# 대기행렬 모델을 활용한 강화학습 기반 파드 오토스케일링 기법

## Abstract

오프라인에서 학습한 모델을 온라인 환경에 적용하여 운영비용 최소화

## 1 Introduction

HPA(Horizontal Pod Autoscaler)

- scale in/out(파드 수 증가/감소 - 수평적 변화)

VPA(Vertical Pod Autoscaler)

- scale up/down(파드의 자원 할당량 증가/감소 - 수직적 변화)
  

## 3 오토스케일 시스템 모델링

CPU 이용률과 만료된 요청 수를 예측하기 위해 [5]의 연구에서 사용된 “Discrete-Time Model for HPA” 기반의 시뮬레이터를 제안

### 시나리오

사용자의 요청은 실시간성이 요구되며 요구되는 응답시간 내에 받지 못한 응답은 불필요하다고 가정

정적 페이지를 반환해주는 Node.js 웹 애플리케이션을 사용

실시간성 요청은 아니지만 Istio[16]의 timeout 설정을 통해 특정 시간 내에 처리되지 못하는 요청을 만료시킴으로써 실시간성을 가지도록 함

Metrics Server는 파드의 자원 사용에 대한 정보 수집, 최종적으로 Prometheus에 수집

도착하는 요청 수는 istio_ requests_total에서 응답코드가 “200”인 요청 수

응답시간이 만료되는 요청 수는 istio_request_total에서 응답 플래그가 “DC”인 요청 수

### 애플리케이션 성능 모델링

웹 애플리케이션에서 하나의 파드가 1초 동안 최대로 처리할 수 있는 요청 수를 측정하기 위해 초당 요청 수(Request Per Seconds, RPS)를 증가시키며 전체 파드에서 처리된 요청 수(served Query Per Seconds, QPS)를 측정하여 가장 큰 값을 기록

측정이 끝나면 파드 수를 증가시키고 증가된 파드 수에 대응하는 최대 QPS를 측정하는 과정 반복
