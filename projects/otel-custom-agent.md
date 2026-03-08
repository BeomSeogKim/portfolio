# OpenTelemetry Custom Agent 개발

> 2025.12 ~ 2026.01 · 단독 설계 및 개발, 전사 적용 주도

`Java` `Byte Buddy` `OpenTelemetry SDK` `Grafana`

**30개 이상 JVM 서비스 전체 적용, 장애 원인 파악 시간 20~50분 → 5분 이내**

<br/>

## Background

- 기존 APM(Pinpoint)이 2일 주기로 다운(저장 용량 초과)되어 제거 결정 후, 모니터링 공백 상태 지속
- LGTM 인프라(Loki, Grafana, Tempo)는 도입되었으나 계측 도구 부재로 실질적 모니터링 불가

<br/>

## Approach

### Spring Boot 버전 제약을 우회하는 Java Agent 방식 선택

- 표준 라이브러리(spring-boot-starter)는 Spring Boot 2.6+ 요구, 사내 서비스 대부분 미충족
- 소스 코드 수정 없이 JVM 기동 시점에 바이트코드를 주입하는 Runtime Instrumentation 방식으로 버전 무관 적용

### 비즈니스 컨텍스트 주입을 위한 Custom Extension 개발

- 표준 Agent는 http.route, status_code 등 인프라 지표만 수집 → "어떤 유저가 문제인가"는 여전히 블랙박스
- JVM 런타임 메모리에 접근하여 UserID를 추출하고 Trace Attributes로 주입하는 Extension 개발
- MVC(RequestContextHolder)와 WebFlux(ServerWebExchange) 환경을 런타임에 감지하여 전략 자동 전환

### N+1 쿼리 탐지기 개발

- 전체 쿼리 스택 추적 시 런타임 성능 저하 우려 → 3단계 Progressive Detection 파이프라인 설계
  - Phase 1: 임계값 미만 시 즉시 반환
  - Phase 2: SQL 정규화 후 해싱으로 반복 패턴 식별
  - Phase 3: 상위 15개 프레임만 검사하여 루프 감지

### 운영 안정성 확보

- 개발 서버 적용 시 Slf4j 로딩 시점 차이로 NoClassDefFoundError 발생 → JDK 내장 java.util.logging으로 래핑하여 외부 의존성 제거
- 관측 도구가 대상 시스템에 영향을 주지 않도록 모든 로직을 Double try-catch로 감싸 Fail-Safe 처리

### 리소스 효율화

- Liveness Probe, Redis Heartbeat 등 인프라 노이즈가 전체 트레이스의 90% 이상 차지
- Agent 단계에서 생성을 원천 차단하는 HealthCheckSampler 구현, 노이즈 90% 이상 제거
