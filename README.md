# 김범석 · Backend Engineer

**문제의 원인을 짚고, 해결 방향을 구체화해 서비스에 구현하는 백엔드 개발자입니다.**

- 중단된 이관 프로젝트를 이어받아 신규 시스템을 출시하고, 데이터 정합성과 조회 병목을 개선합니다.
- AI의 구현 계획과 결과를 검토하며 개발·검증에 활용합니다.

[![Blog](https://img.shields.io/badge/Blog-addylog.dev-333333?style=flat&logo=rss&logoColor=white)](https://addylog.dev)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat)](https://www.linkedin.com/in/beomseogkim/)
[![Email](https://img.shields.io/badge/Email-555555?style=flat&logo=gmail&logoColor=white)](mailto:dev.adrianstudio@gmail.com)

## 경력

**트렌비 · 백엔드 엔지니어** · 2024.05 ~ 현재<br>
도메인: 전시 · 마케팅 · 글로벌 · 리세일

## 대표 경험

### [리세일 시스템 마이그레이션](experience/resale-migration.md)

*2026.02 ~ 2026.05*

> 중단된 프로젝트를 인수해 AI 기반 개발과 데이터 검증을 거쳐 **약 3개월 만에 신규 시스템 출시**.

### [AI 기반 E2E 테스트 유지보수 자동화](experience/self-healing-test.md)

*2026.07 ~ 현재*

> **실패 분석 → 수정·재검증 → PR 생성**을 자동화하고, 사람이 검토·반영하는 유지보수 체계 구축.

### [한달특가 재구축](experience/monthly-special.md)

*2026.06*

> **멱등 처리·보상·Outbox 재처리**로 중복 할인과 서비스 간 부분 실패에 대응하도록 재구축.

### [매입전환 경로 구축](experience/purchase-conversion.md)

*2026.07 ~ 2026.08*

> **고객 직접 신청 경로**를 구축하고, 지연·중복 이벤트 방어와 실패 단계별 보상·운영 복구 설계.

## 연동·성능·운영 개선

| 경험 | 해결한 문제와 결과 |
| --- | --- |
| [eBay 상품 연동 자동화 및 고도화](experience/ebay-global-integration.md) | 수기 등록을 MIP 일괄 등록, 다국가 API 연동으로 단계적으로 확장. **전체 상품·전 국가 연동 약 24시간 → 3시간** |
| [C2B 경매 서비스 개발](experience/c2b-auction.md) | 백엔드 전반을 단독 담당. 업무 규칙을 구체화하고 도메인 모델·테스트로 기획 변경에 대응해 **약 2개월의 최초 출시 목표** 달성 |
| [기획전 조회 성능 개선](experience/exhibition-performance.md) | 순차 상품 조회 병렬화와 요청 기반 캐시 갱신. **캐시 미스 시 약 30초 → 2초**, 배포 후 3~4일간 지연 알림 미관찰 |
| [쿠폰 조회 성능 개선](experience/coupon-optimization.md) | N+1 해소와 반복 COUNT 쿼리 통합. **결제의 사용 가능 쿠폰 약 12초 → 0.3초**, 전체 사용자 대상 약 5초 → 1초 |
| [개인화 추천·이벤트 처리 개선](experience/user-behavior-data.md) | 추천 API·A/B 분기와 사용자 행동 이벤트 파이프라인 구축. 배치 처리로 전송 적체를 줄여 추천 학습 데이터의 최신성 회복 |
| [OpenTelemetry 분산 추적 적용](experience/otel-custom-agent.md) | Spring Boot 플러그인의 버전 제약을 Java Agent로 해소. Custom Extension으로 사용자·주문 단위 추적과 N+1 탐지 지원 |
| [초저가 기획전 자동화](experience/budget-exhibition.md) | MD가 매일 수작업으로 갱신하던 상품을 주기적으로 자동 반영 |

## 개인 프로젝트

- **[Partitur](https://github.com/BeomSeogKim/Partitur)** — 여러 AI 코딩 에이전트의 역할·실행 순서·인수인계를 관리하는 도구
- **[sealbox](https://github.com/BeomSeogKim/sealbox)** — AI 에이전트와 개발할 때 시크릿을 보호하는 로컬 암호화 저장소

## 오픈소스 기여

- **OpenSearch** — if-else 체인을 switch 표현식으로 전환하고 사용 종료된 upgrade-cli 도구·빌드 참조 제거 · [#18965](https://github.com/opensearch-project/OpenSearch/pull/18965) · [#18494](https://github.com/opensearch-project/OpenSearch/pull/18494)
- **Spring AI** — JSON 파서에서 int/long의 과학적 표기법 처리 개선 · [#3051](https://github.com/spring-projects/spring-ai/pull/3051)
- **Mockito** — JDK 21 Sequenced Collections 지원 추가, 리뷰에 따라 테스트를 프로젝트 표준 Assume.assumeThat 방식으로 개선 · [#3708](https://github.com/mockito/mockito/pull/3708) · [#3711](https://github.com/mockito/mockito/pull/3711)

## 학력

**연세대학교 환경공학과**

- 석사 · 2020.03 ~ 2022.08
- 학사 · 2014.03 ~ 2020.02 · 수석졸업

---

[이전 학습·부트캠프 프로젝트](Archive/README.md)
