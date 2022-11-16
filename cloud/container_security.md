# 컨테이너 보안

컨테이너와 쿠버네티스를 사용함에 있어서 보안(Security)와 관측가능성(Observability), 즉 가시성 확보가 중요함

**Calico**

다양한 Cloud Native환경에 손쉬운 접근 Ingress/Egress 보안, 보안 및 규정 준수, Observability 및 Troubleshooting이 가능함

WireGuard 암호화, 승인되지 않은 연결에 대해 알림

단순하고 편리함



인가된 연결만 허용, 그렇지 않은 연결은 침입으로 간주하여 알람 발생

정책 우선 단계 : InfoSec -> 플랫폼 -> 애플리케이션

정책 관리는 서비스마다 label을 정의하여 관리할 수 있음

정책 적용 방법 : Calico에서 제공하는 대시보드 사용, yml 파일 작성

같은 영역 내에서 통신하는 경우 ingress와 Egress 규칙을 설정할 수 있음



네트워크 관련 이슈 확인, 디버깅을 위한 패킷 캡처(스케줄 설정)

ip와 pod를 매핑시켜야 하는 경우 endpoint 보고 찾을 수 있음
