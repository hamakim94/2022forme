# 22/02/09

## 알고리즘

- 문제 해결 방법!!
- 유한한 단계를 통해 문제를 해결하기 위한 절차나 방법
  - 컴퓨터 : 어떤 일을 수행하기 위한 단계적 방법

### 표현 방법

- 의사코드(Pesudocode)
- 순서도 
  - 자연어, 코드 

---

### 목적

- **정확성 : 정확하니?** : 지금 우리의 목표! 결과만 나오자
- 작업량 : 적은 연산으로 원하는 결과를!
- 메모리 사용량 : 적은 메모리 사용!
- 단순성
- 최적성 : 개선할 여지 없이 최적화됐나!

---

### 알고리즘의 작업량 : 시간복잡도!

- 시간 복잡도(Time complexity)
  - 실제 걸리는 시간을 측정
  - 실행되는 명령문의 개수를 계산.
    - 대입 : 연산 1번

~~~ pseudocode
CalcSum(n){
    sum = 0; // 1번
 	for (i <- 1, i<=n, i <- i+1) //비교 1번 i증가 1번
        sum <= sum + 1  // 누적합 1번 => 이것들 총 n번
    return sum
}
// 총 3n + 1
~~~

- 빅-오 표기법(Big - Oh Notation)
  - 시간복잡도 함수 중에서 가장 큰 영향력을 주는 n에 대한 항만 표시
  - 계수는 생략하여 표시!
  - 위 문제, (3n + 1) => O(n) : 
    - n만 표시 -> O(3n)
    - 계수 생략 -> O(n)

- O(1) -> O(logn) -> O(n) -> O(nlogn) -> O(n^2) -> O(2^n) -> O(n!)

- log의 밑은 항상 2다
- 크기를 넣을 땐 항상 큰 수를 넣고 비교해

## 배열

- 일정한 자료형의 변수들을 하나의 이름으로 열거하여 사용하는 자료구조

### 필요성

- 여러개의 변수가 필요할 때, 일일이 다른 변수명 -> 비효율
- 하나의 선언 -> 여러 변수 선언
- 다수의 변수로는 하기 힘든 작업은 배열을 활용해 쉽게!

### 기타

- 코드 역순회 할때, arr[N-i-1] 이 아니라 arr[N-1 -i] 로 쓰자
  - 앞에껀 직관적이지 않아

- ctrl + y : 실행 취소의 취소(ctrl + z 취소)

---

### 문제 완벽풀기 5단계(SWEA)

1. 지문을 읽는다(아주 꼼꼼하게 읽는다.. 소설, 웹툰 아님!)
2. 문제를 이해한다(음.. 어떤 접근법을 써야겠군 )
3. 문제를 손으로 푼다(**손으로** !!)

------------------손으로!!!---------------------------------

4. 푼 걸 코딩한다 ( 이게 안 돼? -> 1로)

5. 디버깅하고 검증한다

**주의** : 이 조건이 여기있었다니!! => 문제를 제대로 안 읽었다는 뜻.

---

## 정렬

### 정의

- 2개 이상의 자료를 특정 기준에 의해 작은 값부터 큰값(오름차순,ascending) 혹은 그 반대의 순서대로(내림차순, descending) 재배열
- 키
  - 자료를 정렬하는 기준이 되는 키값

---

### 정렬

- 버블정렬

- 선택  정렬
- 카운팅 정렬
- 삽입 정렬
- 병합 정렬
- 퀵 정렬

---

### 버블 정렬

#### 정의

- 인접한 두 개의 원소를 비교하며 자리를 계속 교환
- 과정
  - 첫번째 원소부터 **인접한 원소**끼리 계속 자리를 교환하면서 맨 마지막 자리까지 이동한다(오름차순)
  - 한 단계가 끝나면 가장 큰 원소가 가장 마지막 자리로 정렬된다
  - 교환하며 자리를 이동하는 모습이 물 위에 올라오는 거품 모양과 같다고 해서 버블 정렬이라고 한다.
- 시간 복잡도
  - O(n^2)

---

###  셀렉션 알고리즘

####  정의

- 저장돼있는 자료로부터 k번째 큰, 혹은 작은 원소를 찾는 방법을 말함
  - 최소, 최대, 중간값을 찾는 알고리즘을 의미하기도 함
- 선택 과정
  - 정렬알고리즘을 이용해 자료 정렬하기
  - 원하는 순서에 있는 원소를 가져오기
- k번쨰 작은 원소 찾기
  - 1부터 k번쨰까지 작은 원소까지 찾아 배열의 앞쪽으로 이동. k번째 반환
  - k가 비교적 작을때 유용, O(kn)의 수행시간 ( k번만 하니까 )
  - 포켓볼 정리 -> 이게 셀렉션 알고리즘

---

### 선택 정렬

#### 정의 

- 주어진 자료들 중 가장 작은 값의 원소부터 차례대로 선택해 위치를 교환
  - 셀렉션 알고리즘을 전체로
- 과정
  - 주어진 리스트 중 최소값 찾기
  - 그 값 맨 앞 위치한 값과 교환
  - 맨 처음 위치를 제외한 나머지 대상으로 반복
- 복잡도
  - O(n^2)

#### 주의

- 버블정렬 : 중간중간 스왑
- 선택정렬 : 인덱스를 다 갖고놀고, 그 후에 swap 1번씩..

---

### 완전검색

#### 정의

- 완전 검색 방법은 문제의 해법으로 생각할 수 있는 모든 경우의 수를 나열해보고 확인하는 기법
- Brute-force, Generate-and-Test 기법이라고도 불림
- 모든 경우의 수를 테스트 한 후, 최종 해법을 도출
- (경우의 수가 상대적으로 작을 때 유용)



- 모든 경우의 수를 생성하고 테스트, 수행 속도 느리고 해답을 찾아내지 못할 확률이 작아.

- **자격검정평가 -> 일단 완전 검색으로 접근(A형), 해답 도출 => 다른 알고리즘 사용(B형)**

---

###  탐욕 알고리즘

#### 정의

- 최적해를 구하는 데 사용되는 근시안적인 방법
- 여러 경우중 하나를 결정해야 할 때, 그 순간에 최적이라고 생각하는것을 선택해 나가는 방식으로 진행하여 최종적인 해답에 도달
- 각 선택 시점에서 이뤄지는 결증은 지역적으론느 최적이지만, 그 선택을 계속 수집하면 최종적인 해답을 만들었다고 해 그것이 최적이라는 보장이 없다
- **일반적으로 머리속에 떠오르는 생각을 검증없이 바로 구현하면 Greedy 접근이 된다**



- 거스름돈 줄이기~
  - 해 선택
  - 실행 가능성 검사
  - 해 검사



- 똑같은 코드도 내가 처음 보는 코드처럼!!



# 22/02/11

## 2차원 배열

### 선언

- 2차원 이상의 다차원 배열은 차원에 따라 Index[]로 선언
- 세로길이(행의 개수), 가로길이(열의 개수)를 필요로 함

4차원의 활용

\[행1][열1]\[행2]\[열2] 에 체크를 했다!로 쓰이는 경우가 있긴 함

---

### 배열의 순회

- nXm 배열의 n*m개의 모든 원소를 빠짐 없이 조사하는 방법
- 행 우선 순회

- 인덱스 잘 가지고 놀 줄 알아야함(천천히 여유를 가지고 생각하자..)

// j와, M-1-j를 한번에 쓰고싶어
// 그럼 2로 나눈 나머지를 활용해서 쓰고싶어
// 따라서 j + (M-1-j-j)*(i%2)

- ++  세로 역방향 순회 / 대각 방향 순회는 어떻게 할래?

---

### 델타 이동

- 델타를 이용한 2차 배열 탐색
  - 4방향 인접요소 돌아~
  - 순서는 상, 하, 좌, 우 ++ 체스도 가능

- 전치행렬
  - 인덱스 조심(다 순회하면 해당 열, 해당 행에서 1번씩 바뀌어 원상태로 됨)
    - i>j로 인덱스 조건을 걸어주면 된다(for문 안에 넣거나, if문을 넣어)

---

## 검색

- 저장되있는 자료 중 원하는 항목 찾기
- 목적하는 탐색 키를 가진 항목을 찾는 것
  - 탐색 키 : 자료를 구별하여 인식할 수 있는 키

---

### 순차검색

- 일렬로 돼있는 자료를 순서대로 검색
  - 가장 간단, 직관
  - 배열, 연결 리스트 등 순차적으로 구현된 자료구조에서 원하는거 찾을 때 유용
  - 알고리즘 비교적 단순, 검색수가 많으면 수행시간이 급격히 늘어나버린다
- 2가지로 나뉨
  - 정렬되어 있지 않은 경우
  - 정렬된 경우

#### 과정

- 첫 번째 원소부터 순서대로 검색 대상과 키 값이 같은 원소가 있는지
- 키 값이 동일하면 그 원소의 인덱스 반환
- 마지막까지 다 보고, 없으면 실패!
- 오름차순으로 정련된 상태
- 자료 순차적으로 검색하자!





cf) for문 익숙 -> while로 해보는 연습



- 찾고자 하는 원소의 순서에 따라 비교회수가 결정
  - 평균 비교 횟수 : (1+2+...+n) *(1/n) = (n+1)/2
  - O(n)

---

### 이진검색

- 자료의 가운데에 있는 항목의 키 값과 비교하여, 다음 검색의 위치를 결정하고 검색을 계속 진행
  - 목적 키를 찾을 때 까지 이진 검색을 순환적으로 반복 수행, 검색범위를 반씩 줄여가 빠르게 검색이 가능해짐
- 이진검색 ? => 자료 정렬!
- O(logN)

#### 과정

- 중앙 원소를 고른다
- 중앙원소 vs 찾고자 하는 목표값
- 목표값이 중앙원소보다 작으면, 왼쪽 반에서 새로 이진탐색, 크다면 오른쪽
- 찾을 때 까지 1~3번 과정 밴복

#### 구현

- 검색범위의 시작점, 종료점 이용
- 자료의 삽입 or 삭제 발생 => 배열의 상태를 항상 정렬로 유ㅜ지

#### 단점

- 정렬돼있는 자료에서밖에 사용을 못함
- 배운 정렬 ? 버블, 선택(O(n^2)), O(logN) 이여봤자 ..

=> 꼭 이진탐색이 최고는 아닌거다!!(정렬돼있지 않은 경우 + 삽입 그런게 있을 때 안 좋을수도)

---

## 카운팅정렬

### 정의

- 항목들의 순서를 결정하기 위해 각 항목이 몇 개씩 있는지 세는 작업
- 선형 시간에 정렬하는 효율적인 알고리즘



- 제한 사항
  - 정수 / 정수로 표현할 수 있는 자료에 대해서만 적용 가능
    - 인덱스를 표현하기 위해서
  - 각 항목의 발생 횟수를 기록하기 위해, 정수 항목으로 인덱스 되는 카운트들의 배열을 사용하기 때문
  - 카운트를 위한 공간을 할당하려면 집합 내의 가장 큰 정수를 알아야함
- O(n+k)
  - 배열의 길이 / 정수의 최대값

- 안정정렬 ? -> 정렬 후에도 정렬 전과 같은 순서로 됨
- + 정렬 숫자에 음수가 껴있으면?

####  단점

- {1,2,10억,1} -> 이만한 사이즈의 배열이 필요함 

####  복수의 원소 카운팅 정렬

- 순서가 유지된 채로 2개의 원소정렬이 가능

