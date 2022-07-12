<p align="center">
    <img width="200px;" src="https://raw.githubusercontent.com/woowacourse/atdd-subway-admin-frontend/master/images/main_logo.png"/>
</p>
<p align="center">
  <img alt="npm" src="https://img.shields.io/badge/npm-%3E%3D%205.5.0-blue">
  <img alt="node" src="https://img.shields.io/badge/node-%3E%3D%209.3.0-blue">
  <a href="https://edu.nextstep.camp/c/R89PYi5H" alt="nextstep atdd">
    <img alt="Website" src="https://img.shields.io/website?url=https%3A%2F%2Fedu.nextstep.camp%2Fc%2FR89PYi5H">
  </a>
  <img alt="GitHub" src="https://img.shields.io/github/license/next-step/atdd-subway-service">
</p>

<br>

# 인프라공방 샘플 서비스 - 지하철 노선도

<br>

## 🚀 Getting Started

### Install
#### npm 설치
```
cd frontend
npm install
```
> `frontend` 디렉토리에서 수행해야 합니다.

### Usage
#### webpack server 구동
```
npm run dev
```
#### application 구동
```
./gradlew clean build
```
<br>

## 미션

* 미션 진행 후에 아래 질문의 답을 작성하여 PR을 보내주세요.


### 1단계 - 화면 응답 개선하기
1. 성능 개선 결과를 공유해주세요 (Smoke, Load, Stress 테스트 결과)
* Smoke 테스트 결과
![smoke_test_result](docs/images/smoke_test_result.png)

* Load 테스트 결과
![load_test_result](docs/images/load_test_result.png)

* Stress 테스트 결과
![stress_test_result](docs/images/stress_test_result.png)

2. 어떤 부분을 개선해보셨나요? 과정을 설명해주세요
* 테스트 했던 경로는 `/path`와 `/stations` 입니다.
1. Gzip 압축으로 정적 리소스 압축 하여 전송 용량 최적화.  
![](docs/images/gzip.png)
2. 정적리소스 캐싱 활용하여 요청 수 최소화.  
![](docs/images/x-proxy-cache.png)
3. HTTP/2 프로토콜 적용  
![](docs/images/HTTP2.png)

4. /stations API 데이터 베이스 조회 Redis 캐싱
* 서비스 레이어 캐시 적용  
![](docs/images/redis1.png)  
* LocalDateTime 파싱을 위한 JsonSerialize/JsonDeserialize 적용  
![](docs/images/redis2.png)  
* 캐시 설정  
![](docs/images/redis3.png)  
* Redis 서버 설정 프로퍼티  
![](docs/images/redis4.png)  
* Redis 서버 Docker 프로세스  
![](docs/images/redis5.png)  

---

### 2단계 - 스케일 아웃

1. Launch Template 링크를 공유해주세요.

2. cpu 부하 실행 후 EC2 추가생성 결과를 공유해주세요. (Cloudwatch 캡쳐)

```sh
$ stress -c 2
```

3. 성능 개선 결과를 공유해주세요 (Smoke, Load, Stress 테스트 결과)

---
### [추가] 1단계 - 쿠버네티스로 구성하기
1. 클러스터를 어떻게 구성했는지 알려주세요~ (마스터 노드 : n 대, 워커 노드 n대)

2. 스트레스 테스트 결과를 공유해주세요 (기존에 container 한대 운영시 한계점도 같이 공유해주세요)

3. 현재 워커노드에서 몇대의 컨테이너를 운영중인지 공유해주세요

---

### [추가] 2단계 - 클러스터 운영하기

1. kibana 링크를 알려주세요

2. grafana 링크를 알려주세요

3. 지하철 노선도는 어느정도로 requests를 설정하는게 적절한가요?

4. t3.large로 구성할 경우 Node의 LimitRange, ResourceQuota는 어느정도로 설정하는게 적절한가요?

5. 부하테스트를 고려해볼 때 Pod은 몇대정도로 구성해두는게 좋다고 생각하나요?

6. Spinaker 링크를 알려주세요.
