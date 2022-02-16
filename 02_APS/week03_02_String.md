# 22/02/14

## String

여러개 문자 중 단어 찾기

- 반복문을 돌면서 첫 글자
- 8방향 돌면서 맞는지 챠챠챡 확인

---

### 컴퓨터에서 문자 표현(이야기~)

- 글자 A를 메모리에 저장하는 방법에 대해서 생각해보자
- 그냥 A라는 모양 새기는거 아니다
- 영어가 대소문자 합쳐서 52, 6비트(64가지)면 모두 표현 가능, 이를 코드 체계라고 한다.



- 네트워크 발전되기 전, 미국의 각 지역별로 코드체계를 정했지만 네트워크가 발전하며 서로간에 정보(미국)를 주고 받을 때 달리 해석하는 문제가 생김
- 표준안이 필요해!
- 1967년 미국에서 ASCII(American Standard Code for Information Interchange) : 문자 인코딩 표준
- 7bit 인코딩, 128 문자 표현, 33개 출력 불가능한 제어 문자 + 공백을 비롯한 95개의 출력 가능한 문자들로!
  - ASCII(문자) 3대장 , 영어(26), 숫자10개
    - 0 : 48
    - A : 65
    - a : 97
- 오늘날의 대부분의 컴퓨터는 문자를 읽고 쓰는데 ASCII 형식 사용
  - 그런데 컴퓨터 발전, 미국 뿐 아니라 다른나라에서도 코드체계 각자 만드는 문제점 발생
- 다국어 처리 -> 유니코드 만들어짐
- 그런데, 유니코드도 2가지 처리방식이 있어서, 뭐가뭔지 몰라!
- 유니코드 인코딩(UTF : Unicode Transformation Format)

---

### Java에선 어떨까?

- String str="abc" : Constant Pool :이라는 곳에 저장돼
  - String str2 = "abc", 라고 하면 Constant Pool에 있는 "abc" 주소로
- String str3 = new String("str"); : new를 사용하면 heap에 저장돼
  - sysout(str3 == str2) 하면 false(주소 달라), 그래서 .equals() 해야지 같은지 봄!
  - String에서 equals는 Object에서 override해서 사용함

- .hashcode()하면 특정 계산을 해서 해쉬코드값을 계산해줌.



- 문자열은 + 연산 가능
- 문자열의 불변성(immutable)
  - +연산을 하면, 메모리에 새로운 문자열이 생겨서 주소를 할당받고
  - 가비지 컬랙터가 안 쓰는거 가져감

---

### 문자열 뒤집기

- 회문, 펠린드롬
  - 반복문(뒤에서 읽기)
  - SWAP ( tochararray로 배열을 만들어서 스왑)
    - 길이의 절반만 swap
  - StringBuilder(스레드 동기X), StringBuffer(스레드 동기) : muttable
    - .reverse() 
    - .append하면 알아서 바뀌니까, 새로운 주소를 만들고 다시 주소 반환하는게 아님, 그래서 빠름



1. 자기 문자열에서 뒤집는 방법이 있고, 새로운 빈 문자열을 만들어 뒤에서부터 읽어 쓰기
2. 자기 문자열 이용 : swap을 위한 임시 변수 필요, 반복 수행을 문자열 길이 / 2 만큼만 수행



- 문자열 -> 숫자로 , 숫자 -> 문자열 : 직접 고민해보기 ( char를 잘 활용하자 )



---

## 패턴 매칭

- 고지식한 패턴 검색 알고리즘(Brute Force)
  - 본문 문자열을 처음부터 끝까지 차례대로 순회하면서 패턴 내의 문자들을 일일이 비교하는 방식으로 동작
  - N(전체 길이) - M(패턴 길이) + 1
- 보이어-무어
  - 오른쪽에서 왼쪽으로 비교
  - 대부분 상용 SW에서 채택하고 있는 알고리즘
  - 패턴 오른쪽 끝에 있는 문자가 불일치 하면, 패턴의 길이만큼 점프하고 다시 확인

- 시간복잡도
  - 최악의 경우 텍스트의 모든 위치에서 패턴을 비교해야 하므로 O(MN)



---

- 카프-라빈 알고리즘(해쉬) -------- 나중
- KMP 알고리즘 => 행렬 ------------나중     OUCH!

---

## 참고) 문자열 암호화(가벼운 마음, 듣고 흘려~)

- 시저 암호
  - 줄리어스 시저 사용, 기원전 100년경 로마활역
  - 평문 알파벳을 일정한 문자 수만큼 평행이동 시켰음
- 단일 치환 암호(문자 변환표)
  - 문자 총 26개니(0 : 46 A 65 a 97) 
  - 총수 : 26!가지(,,,())
- bit열의 암호화
  - exclusive or(같으면 0, 다르면 1 )
  - 다시 돌리기? -> (a+1%2), 1-a,  등등
- 저장소의 크기를 줄이며 정확한 정보 저장?
  - Run-lenght-encoding 알고리즘
  - 같은 값이 몇번 반복되는가를 나타냄
  - 이미지 파일포맷 중 BMP 파일포맷의 압축 방법(ABABAB/ : 비효율)
    - 효울적인 방법?
      - 허프만 코딩 알고리즘(음 이런게 있다..)
