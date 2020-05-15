# 지하철 경로 조회 - TDD

## 실습 - 지하철 노선도 조회

### 🐱 저장소
 - https://github.com/woowacourse/atdd-subway-path
 
### 요구사항
 - 모든 지하철 노선과 각 노선에 포함된 지하철역 조회 기능 구현
 - 인수 테스트와 단위 테스트를 작성
 - 페이지 연동 
 
### 기능 목록
 - [x] 지하철 노선도 페이지 조회
 - [x] 모든 지하철 노선과 지하철역 목록을 조회
 - [x] 지하철 역 간의 최단 거리 조회
    - [x] 최단 거리와 최소 시간으로 조회

### 시나리오

```
Feature: 전체 지하철 노선도 정보 조회

  Scenario: 지하철 노선도 정보 조회를 한다.
    Given 지하철역이 여러 개 추가되어있다.
    And 지하철 노선이 여러 개 추가되어있다.
    And 지하철 노선에 지하철역이 여러 개 추가되어있다.
    
    When 지하철 노선도 전체 조회 요청을 한다.
    
    Then 지하철 노선도 전체를 응답 받는다.
```

```
Feature: 지하철 경로 조회

  Scenario: 지하철 경로 조회를 한다.
    Given 지하철역이 여러 개 추가되어있다.
    And 지하철 노선이 추가되어있다.
    And 지하철 노선에 지하철역이 여러 개 추가되어있다.
    And 출발역과 도착역을 입력받는다.
    
    When 지하철 경로 조회를 한다.

    Then 가장 빠른 경로를 응답 받는다.
```

### 구현 순서

 - 인수 테스트 작성
 - 단위 테스트 작성
 - 뷰 연동
    - 모달 열기
    - 버튼 리스너
    - 스크립트 수정 및 예외처리
 - 예외처리 및 Side 케이스
    - [x] 출발역과 도착역이 같은 경우
    - [x] preStation이 null인 시작 간선이 없을 경우
    - [x] 빈 값이 들어올 경우
    - [x] 출발역과 도착역이 연결되어 있지 않은 경우
    - [x] 존재하지 않는 출발역이나 도착역 이름을 조회할 경우