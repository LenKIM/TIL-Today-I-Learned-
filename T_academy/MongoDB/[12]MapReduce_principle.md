학습목표
1. 맵 리듀스의 개념과 정의
2. Hadoop의 특징과 MongoDB의 맵 리듀스와의 관계를 이해할 수 있습니다.
----

1. 맵리듀스란?
  - 대용량의 데이터를 안전하고 빠르게 처리하기 위한 방법
  - 한 대 이상의 하드웨어를 활용하는 분산 프로그래밍 모델
  - Hadoop은 HDPS이라는 대규모 분산 파일 시스템을 구축하였음


![스크린샷 2017-04-07 오전 10.06.46](http://i.imgur.com/TH870mJ.png)
  **맵 리듀스 특징**
  - 맵 리듀스는 데이터를 분산하여 연산하고 다시 합치는 기술
  - 맵과 리듀스 단계로 나누고 맵 단계는 입력과 출력으로 Key-Value의 형태로 가지고 있음
  - 데이터를 섞어서 병합하고 리듀스 함수를 통해 최종적으로 결과를 제공함
  - 맵과 리듀스는 사용자가 임의로 코딩이 가능한 형태로 제공
  - 분산을 통해 분할된 조각으로 처리한뒤 다시 모아 휠씬 짧은 시간에 계산을 완료함
  - 분활된 조각이 작으면 작을수록 부화 분산에 더 좋은 효과를 냄
  - 너무 과하게 데이터를 분할할 경우 맵을 생성하기 위한 태스크의 오버헤드가 커지기 때문에 역효과가 날 수 있음

  |장점|단점|
  ---|---
   분산 모델을 감추어 대용량 처리에 단순하게 만듦 | 기존 RDBMS보다 불편한 스키마와 질의
   특정 데이터 모델이나, 스키마에 외존적이지 않은 유연성 | DBMS와 비교하여 낮은 성능
   저장구조의 독립성 | 개발환경의 불편함과 운영 노하우 부족
   높은 확장성 | 단순한 데이터 처리

   ![스크린샷 2017-04-07 오전 10.13.42](http://i.imgur.com/Bz8nQjj.png)

   ![스크린샷 2017-04-07 오전 10.15.11](http://i.imgur.com/xMXXd6u.png)

2. Hadoop의 HDFS, 맵 리듀스
  - HDFS 개요
  **구성 요소**
  - 클라이언트: 데이터 송수신 요청
  - 네임 노드: HDFS전체 시스템 제어
  - 데이터 노드 : 수천대의 서버로 구성, 데이터 저장 역할

  **데이터 처리 원칙**
  - Block size : 파일을 저장하는 단위(64MB or 128MB)
  - Replication : 모든 블록은 여러 노드에 분산되어 저장(기본 3개)

![스크린샷 2017-04-07 오전 10.17.54](http://i.imgur.com/233Tusg.png)

![스크린샷 2017-04-07 오전 10.20.43](http://i.imgur.com/Zll5pKk.png)

![스크린샷 2017-04-07 오전 10.24.33](http://i.imgur.com/qaR9DSa.png)

![스크린샷 2017-04-07 오전 10.27.06](http://i.imgur.com/k1A4zVO.png)

![스크린샷 2017-04-07 오전 10.29.50](http://i.imgur.com/B0LPNMi.png)

![스크린샷 2017-04-07 오전 10.30.29](http://i.imgur.com/YwcOwEl.png)

**Hadoop의 맵 리듀스**
- 설계 특성
    - 분산 컴퓨팅에 적합한 함수형 프로그래밍
    - 배치형 데이터 처리 시스템
    - 어플리케이션 로직의 주요관심사를 파악, 많은 요소를 반영
- 주요 기능
    - 자동화된 병렬 처리 및 분산처리
    - Fault-tolerance(내고장성,결함허용)
    - 상태 및 모니터링 툴들
    - 프로그래머를 위한 추상클래스

**맵리듀스 과정**
  - 원복데이터는 Map함수에 의해서 <Key, Value> 쌍으로 전환됨
  - Map()함수: 입력을 출력Key와 과련되는 1..N개의 <Key, Value>를 생성
  - Map 단계 다음에서 출력 Key의 중간 Value들은 하나의 리스트로 함쳐짐
  - Reduce()함수 : 같은 출력 Key를 가지는 final value를 중간 value들로 통합

![스크린샷 2017-04-07 오전 10.37.14](http://i.imgur.com/Ik9Bmji.png)


![스크린샷 2017-04-07 오전 10.38.44](http://i.imgur.com/yLVI6ek.png)

3. MongoDB의 맵 리듀스
**특징**
- MongoDB는 빅데이터 처리를 위한 다양한 기능들을 제공함
- MongoDB는 관계형 데이터베이스에서 흔히 제공하는 데이터 집계합수들을 지원하고 있지않음
- 기존 관계형 데이터베이스 입장에서 보면 굉장히 불편함
- MongoDB에서는 집께 함수를 지원하지 않는 대신 MapReduce를 통해서만 집께 구현 가능(다른 솔루션의 MapReduce와는 다른 특징)

![스크린샷 2017-04-07 오전 10.42.33](http://i.imgur.com/JH6q8IF.png)