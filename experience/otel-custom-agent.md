# OpenTelemetry 기반 분산 추적 적용

> 기간: 2026.01
> Java Agent와 Custom Extension으로 레거시 서비스의 APM 적용 제약 해소

APM 도구가 부재한 MSA 환경에서 문제 원인을 파악하려면 여러 서비스의 호출 흐름을 직접 추적해야 했습니다. 기존 Tempo·OpenTelemetry Spring Boot 플러그인 기반 도입은 사내 대부분 서비스가 최소 버전 요구사항을 충족하지 못해 중단된 상태였습니다.

OpenTelemetry Java Agent 기반으로 전환해 프레임워크 버전 업그레이드 없이 분산 추적을 적용했습니다. Custom Extension으로 userId·orderId 추출과 N+1 탐지 기능을 추가해, 사용자·주문 단위의 문제 추적과 반복 쿼리 확인을 지원했습니다.

---

[← 포트폴리오](../README.md)
