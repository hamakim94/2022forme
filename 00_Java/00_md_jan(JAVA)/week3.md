# 2022.01.17

## Java 기초

- 컴퓨터 기초

  - x86 : 옛날에 컴퓨터(인텔)은 cpu명이 286 386 .. 등으로 나왔따
  - 팬티엄 2? 부터 32bit(4byte)를 기본, 애초에 ip도 4바이트
  - 그래서 x86 ~ 써있으면 대충 32bit, 나중에 x64

- 1KB => 1024Byte

- 1 MB => 1024KB

- 1 GB => 1024MB  

  - 따라서 램 4Gb => 4,294,967,296 바이트  == 2^32, 즉 32비트 체제의 한계는 렘 4기가
  - *** 주소는 1씩 증가할때마다 1byte, 데이터는 1씩 증가할때마다 1bit 증가***

  

- 잡지식
  - 1G : 아날로그 통화
  - 2G : 문자
  - 3G : 영상통화
  - 4G : IP통신, ALL IP(통화하고 바로끄면 기록이 안 남는데, IP로 지정되면 남아.)

- 키보드
  - 보통 키보드가 7비트(128개 정도 써,) => 그래서 ASCII코드가 나온 것



- String 자료형은 특이하다. 분명 참조형인데 syso가 가능하다...

---

### 입력받는 법(for 알고리즘)

- Scanner

~~~java
// 입력을 받기 위해 입력을 도와줄 객체가 필요
		// ctrl + space + o : import
		Scanner sc = new Scanner(System.in); 
		
		// bool
		boolean flag = sc.nextBoolean();
		// 문자 하나만 불가, 
		// char a = sc.nextChar()????
		
		// 정수형 입력
		byte bnum = sc.nextByte();
		short num = sc.nextShort();
		int age = sc.nextInt();
		long money = sc.nextLong();
		
		// 실수형 입력
		float fnum = sc.nextFloat();
		double dnum = sc.nextDouble();
		
		// 문자열 종류 파악하기
		String name = sc.next();
		
		//문자 하나만을 입력받고싶으면
		char c = sc.next().charAt(0);
		
		System.out.println();
~~~

---

- Java에서 / 기호는 몫이다.
- 그래서 1의 자리수 내림을 한다면, 

~~~java
int a = 27;
age = a / 10 * 10(20대);
age = a - (a % 10)
~~~

- 반올림 쉽게 하려면, 5를 더한 후 내림을 한다(원하는 자릿수)

---

- do - while 문:
  - 조건문에서 쓰이는 변수가 반복문 안에서 결정될때?(여러번 인풋 받고싶어!)

~~~java
do{
    명령문, while문 안에 들어가는거랑 같아
}while (특정 변수의 조건);
~~~

---

- class 이름 바꾸기 (eclipse 탐색기에서)
  - 우클릭 - refactor - rename, 나중에 모든걸 다 한번에 바꿀 수 도 있음....
    - 즉 다른 클래스 파일에서 해당 클래스를 쓸 때, 모든 파일의 이름을 바꿀 수 있다고!(편하다고!!)

---

- 3항 연산자(자주 쓴다네!)

~~~java
String message = (sth == 1) ? "해삼" : "멍개";
//반환 type = (조건) ? 참일때 return : 거짓일 때 return;  : 반환 type이 중요하다. 반환을 받는 변수같은게 필요하다는겨!
~~~

# 2022.01.18

- APS 만들어야 할 습관
  - 문제 제대로 읽어 이해하기 
  - (필기구로 끄적끄적) 해야할 일 정리
  - IDE에서 주석 넣으며 정리한 일들 쓰며 할 일 정해서 해보기.

- for문의 종류 : (자료형 변수명 : 반복할 수 있는 것) = (for each 문이라고도 불린다)
  - 이건 값을 수정할 수 없는 단점이 있다ㅣ

---

- 단축 평가
  - 논리합 || 
    - a || b , a가 참이면 b 볼 필요 없다
  - 논리곱 &&
    - a && b , a가 거짓이면 b 볼 필요 없다

- 비트연산자 &, | => 컴퓨터니까 그냥 가능해버림! ( 특정 숫자를 10110 01101) 해서 같으면 1 아니면 0 이런식으로 연산 가능!

---

- 블록 안에서 { int a = 0 ;  명령문} 하면 
- a는 } 만나 블록이 끝나면 못 쓰지만, 메모리에는 남아있고, Garbage Collecter 가 돌아야 사라짐

---

- switch case : break문 없으면, 해당 case 밑에 모든 명령문들 다 실행돼(default 포함!)

---

- Integer.MAX_VALUE => 쓰면 최대, 최소 값 구하기 쉬운 편!

---

- XOR -> 두 개가 같으면 1 다르면 0

# 2022.01.19

cf) 클라우드란? (ex) google drive, dropbox(저장 공간), amazone etc()

- 자원(인프라)을 빌려쓰는 것
- 하나의 큰 저장공간을 나눠서 빌려준다~(매번 ssd 사줄 수 없으니까, '근데 CPU는?')
- 나누는 기술이 가상화라고 부른다. 

## 틀린거

- class를 만들땐, 보통 우클릭 클래스 해서 만들어서 main java파일에서 사용
- 와.. 클래스 자체의 멤버 변수를 선언을 안 해도 일단 실행이 돼., 심지어 변수도 안 정해도
- =>  heap 에 있어서(new 때문에), 아.. 선언 하면 알아서 기본생성자 넣는다!
- 그래서 걍 멤버변수 선언만 돼있으면 설정하지 않아도 .변수로 부를 수 있어!

헐.. 생성자도 함수니까 overloading 가능../

이름 + 매개변수 형태까지가 함수의 이름이라고 생각해 ^^ (이름만 다르면 의미 X, String name, String k)

~~~java
new Class().method(); // 실행 가능?
// 가능!! 변수에 담는 행위는 나중에 쓰려고야. 
// new Class() 자체로 인스턴스!!!!! 메서드 사용 가능
~~~

- 갑자기 생성자 만들면, 빨간줄. 그 이유!? => 생성자 만드는 순간 기본생성자 안 생겨

---

#### 내 질문 : 그럼 int[][]에서, 최종적으로 들어가는 자료형태가 int라는건가요?

int[] [] arr = new arr[] []

int [] [] 자체도 하나의 타입!, 마지막에 들어가는게 int라는 뜻!

arr[] 의 타입은 int [] , 또 주소 반환!:  -> int가 아니다! 

#### HW

- 내가만든 array.toString()하면, ? 뭘 toString할건데?
- Array.toString(내가만든배열)이 맞다



## 배열이란? : []

- 같은 타입의 변수의 모임 (같은  타입의 자료를 연속적으로 모아둔 것)

  - 장점 1 :  간편하게 많은 **같은 타입**의 변수를 생성
  - 장점 2 : 연속된 공간을 할당받음

  ​    ( int num = 0; int num= 1 (메모리상에 이곳저곳 생겨짐))

  ​	( 만약 27번지\[칸 \] 31번지 \[칸\] 왜 +4 -> int-4byte니까) , 27번지 + int (27 + 0*4)

  - 장점 3 : "반복문"과의 시너지, 데이터를 인덱스(숫자)로 접근이 가능
  
- 한 번 생성된 배열은 크기 바꿀 수 없음

- **배열의 유형은 모든것이 가능하다** ( 기초자료 8개 + String + int[] +참조형 ,,,,,,)

  - **클래스도 가능하다고!!!!!!!!!!!!!!!!!!!!!!!!!**
  - 배열의 인덱스는 0부터
  - 배열크기 : 배열이름.length
  - 마지막 요소 인덱스 : array.length - 1
  


---

### new => 이거 교수님이 미친듯이 강조하심

~~~java
            int[] num = new int[78]; // 78명의 점수를 담기위한 배열
// 2.num에 주소를 담아  <-  1.공간(int 78개 담아)을 만들고 new에서 주소를 반환해
~~~

- 크기가 정해지지 않아도 괜찮은 데이터를 위한 공간(메모리) 만듦
- new로 만든 공간 -> 이름을 지어줄 수 없음
- 그래서 크기가 정해지지 않은 공간의 위치를 기억한다.
- 그 위치를 기억하기 위해 만든 변수같은 느낌이 int[] ( 이것도 하나의 타입)
- 여기서 위치란 int[78], 즉 배열의 시작점의 주소다.
  - int[] -> **int 배열**의 주소를 담을 수 있음(type)
  - int -> 정수 하나를 담을 수 있음

---

### 두 공간 바꾸기(변수값 교환) : SWAP 이라고 한다

- tmp 변수 만들어서 int tmp = a;
- b = a;
- a = tmp;

- 만약, 최대값 찾고, 공간을 바꿔? -> 계속 반복 ? -> 정렬 가능

---

### for - each : 꺼내서 뭐하고, 꺼내서 뭐하고 - copied value

~~~java
for ( int n : num) {
    // 마치 n = num[0], n = [1], ...
    System.out.println(n);
    // 만약 n을 바꾸면
    n = 123 ; // 이렇게 하면, num 안에있는걸 n에서 복사해서 쓰는거기 떄문에 score 사용 불가
}

// 쉽게  Arrays ctrl + space : 알아서 임포트
 System.out.println( Arrays.toString(num)); // 그냥 문자열만 주는거, 
~~~

### 문자열

- 문자열은 특별취급, new 없어도 됌,
- 상수 메모리라는 공간에 저장
- String type의 기본값 : null, ""는 공백이 아냐!(이상한 실선이 있다고 생각)

---

### 최대값 찾기 -> 굳이 언급한 이유가 있음

만약, 최대값 찾고, 공간을 바꿔? -> 계속 반복 ? -> 정렬 가능

---

### 안 정해진 공간(heap)

- 여기선 초기값 무적권 정해짐, null :  없음

### 이차원 배열

---

- int [] [] = new int [3] [2]  like 3*2 행렬, 2번쨰 리스트 안에는 설정 안 해도 되고, 각자 크기 달라도 돼
- int[\][\] 도 하나의 자료형이야! int[], 정수로 이루어진 배열의 주소를 담을 수 있는 또 하나의 배열의 주소!



### 마우스 대면 노란색 박스 읽는법

---

- System.arrayCopy (예시)
- System.toString

메소드명  . 치면 박스 나옴 ->  (필요한 것들:파라미터, 전달인자) : 자료형(반환타입) = 주소(패키지명)

함수명

---

### delta ( 상대적인 위치) - APS

int[] dr = {-1, 0, 1, 0} // row

int[] dc = {0, -1, 0,1} // col

 indexOutOfBounds exception을 예방 => 조건문으로!!!

int \[]\[] drc = { {-1,0}, {1,0} ... } 

if dy dx : 어떤게 행이 x인지, 열이 x인지 파악해야함...

---

## 클래스

### 클래스란?

- 클래스의 첫 글자는 대문자!

- 다른 타입의 데이터들의 모임(일단 시작은.. 클래스의 일부, 개념잡기)
- 우리가 원하는 형태의 자료를 담기위해(?) 개인화된 도장(특이 int[])

~~~ java
public class Person{   // 도장!
    String na; // 써먹을 수 있어
    int ag;    // 멤버 변수 ; 속성 ; 필드 로 불려! => 그런 속성들이 있다~
    int hei;
    
    //생성자 : 매개변수를 받으면, 알아서 멤버변수에 값을 넣어줌
    Person(String na, int ag, int hei){
        this.na = na; // Person의 String na. int 등은, 아래에서 받는 Person 생성자 메소드의 지역변수라고 생각
        this.ag = ag; // 그래서 이름이 같을 때, this(Person Class의 주소)를 정해서 여기에 na가 지역변수 na로
        this.hei = hei; // 값을 준다고 생각하면 돼!
    }
    // 최종적으로 원하는 형태를 마지막으로!
    // 생성자도 함수니, 오버로딩 가능
    Person(){  
        this("kjk", 30, 23); // 다른 생성자를 부를 수도 있어, 보통 최종 형태의 생성자!!!!!
        System.out.println("Hi")    // 다른 실행문 위에, 가장 처음만
    }
    //
    
    // 메소드(멤버 함수, Behavior)
    void print(){
        System.out.println("사람의 이름은 " + na + "입니다")
    }
}
/* 다른문서 */
Person p = new Person(); // new 이후 : 인스턴스!
p.na = "King";
p.ag = 55;
p.hei = 199;
p.print();
~~~

- \*\* 클래스는 관련있는 함수와 변수를 묶어서 만들어낸 **사용자정의 자료형** \*\*
- 모든 객체들의 생산처, 객체를 생성하는 틀
- 객체의 상호작용 : (사람 객체 -> 전원 on <- show 화면 스마트폰 객체) 
- 추상화 -> 클래스를 설계

~~~ java
new Class().method(); // 실행 가능?

// 가능!! 변수에 담는 행위는 나중에 쓰려고야. new Class() 자체로 인스턴스!!!!! 메서드 사용 가능
~~~

---

#### 매개변수와 인자

매개변수(Parameter) : 함수를 정의할때 쓰는거 정의 : eat( 매개변수 )

인자(Argument) :                                                   활용 : cat.eat( 인자 )

---

#### 함수? ..nextInt();

자주 써놓은 명령어들을 묶어서 이름을 붙여놓는것

(이름만 기억하면 돼, 위치를 기억할 필요가 없어, ctrl+f할 필요도 없어)

return : 함수를 호출한 곳에, return 후에 값을 찾아서넣어준다

---

#### 메서드

매개변수의 type을, class형태로 할 수 도 있어!

- 함수도 매번 쓰기 귀찮아 -> Class안에 넣자
  - class안에 변수 있으면, 그냥 쓸 수 있어!
- 이름 + 매개변수 형태까지가 함수의 이름이라고 생각해 ^^



- 매개변수가 있는 함수 ( 생성자 )
  - new Person(a, b, c)

~~~ java
Per(String na, int ag, int hei)
    String na;
	int ag;
	int hei; 랑 같은 의미, 즉 생성자 안에서 새로운 변수를 만들어
        
    그래서 this가 필요하다고!!!!! 객체의 위치에 있는 na를 원하니까
~~~

---

#### 생성자(함수다)

- 객체가 생성될 떄 최초 한 번 실행되는 **함수**
- 클래스와 함수명이 같아야함.
- **반환 유형**이 없다, 처음 실행할 떄 주소를 넣어줘야하는데, void조차 아니다
- 보통 다른 클래스 파일(.java)로 만듦, public 써야겠지
- ** 생성자가 없어> 기본생성자를 컴파일러가 자동으로 만들어줘 **  
  - 그런데 하나 정의하는 순간, 자동으로 만들어주지 않아서 가능한 모든 경우의 수를 다 만들어야함.

- 우클릭 - source - generate constucter;; 생성자 만듬

---

#### 메서드 오버로딩의 조건

- 메서드 이름 같
- 파라미터 달(근데, 자료형만 다르면 안 돼, 순서라도 달라야 정의 가능,)
  - 생성자에서, String 자료형 2개의 변수가 있따
  - 그걸 만들 떄 cat(String new) == cat (String gender) 컴퓨터는 완전 같다고 인식


---

#### this( 나 자신의 위치를 만듦)

- 생성된 객체의 주소를 불러줌

- 함수 안(지역변수)의 주소와 객체 안(멤버변수)의 주소는 다르다.

  

클래스 - 도장 - 객체생성 - 함수 - 함수도 클래스에? - 등등등



# 2022.01.20

## 틀린거

- hw02. 선언과 동시에 초기화 => 한 줄에끝내줄래?

- 문제 똑바로 읽기. 입력받은 인덱스에 값을 넣어주는거.

---

인스턴스 : 클래스를 통해 찍어냄

클래스 : 실생활에 있는 친구를 추상화 => 속성 동작 (필드, 메서드) => 사용자정의 자료형

객체와 인스턴스의 차이는 , 때마다 다르다!

---

- package는 ctrl + 클릭이 안된다, 클릭 되면 그건 클래스!!!
- ctrl shift o => 필요한거 임포트. 필요없는거 지워주고

###  ***\*\*\*\* 0과 1 바꾸기 *\*\*\*\***

- a = 1-a
- a = a^1 : 비트연산자 XOR
  - a ^= 1 (똑같다)
- a *= -1(부호바꾸기)
- 0 1 2 3 0 1 2 순회? -> a = (a + 1) %44 

### CodeUp 1098 설탕과자 뽑기

- 틀렸던 것들
  - 문제에서 굳이 세로, 가로길이 따로 입력받아? -> 다를 수 있음
    - 정방행렬이라고 착각해서 틀림
  - 굳이 정의역 표시한 문제:
    - 잘 따져보고, 항상 문제 이상의 범위가 나오는 경우가 있다
    - 조건문으로 항상 참일 경우만 만들자

- 오류들
  - ArrayIndexOutOfBoundsException(최대값 범위 확인 x)
  - 수정 후 1번째 테스트 케이스도 확인 제대로 안 함, 천천히
  - ArrayIndexOutOfBoundsException(출력할 때)
- 다른사람 코드 보니
  - 그냥 for문의 index는 0부터 시작하고, 기존에 있는 x,y좌표 활용하자!!

---

### CodeUp 1411 빠진거찾기

- for문에서 n-1개 찾는건데 n번 돌아? => 아에 결과가 안 나옴

### CodeUp 1507  4개사각형넓이

- 아.. 넓이를, 그냥 점 1개씩 더한걸로 생각해
- 그러면 그냥 for문 돌면서 1 있으면 넘어가고
- 0이면 1로 바꾸고 전체 넓이 + 1
- 그리고, 사각형의 제일 왼쪽 위(왼쪽 아래) 꼭지점을 1로 해야지 넓이가 온전히 1로 된다.

### 이차원 배열 for-each

~~~java
int [][] nums = {{}, {}, ... }
for (int[] arr : nums){ 
    for(int i=0; i< arr.length;i++){
        arr[i] *= 2;
    }
}
// 이건 복사가 돼!
// arr은, 1차원 배열의 주소를 값복사!
// 복사된 주소에 직접 접근!해서 배열의 값을 하니, 실제 2배가 된다

~~~

- dc dl 2가지 사용법(2차원)
  - 모든 범위 안에 들어올 떄 움직여 ( && && &&)
  - 범위 밖이면 그냥 continue ( || || ||)

### 해보기

- 5*5 배열
- 2칸씩 이동하는 경로를 따라 출력
- 배열을 2개만듬, 만들어준 delta에 * 를 해서 2배 하면 또 출력 가능!



# 2022.01.19

### 질문 / 틀린거

~~~ java
클래스명 (String name, String kk) // => 이건 그냥 순서로 구분
클래스명 (String name)
클래스명 (String kk)     // 구분방법?
~~~

-> 구분 방법 : 밑에 조건문을 써서 어떤 변순지 파악하면 된다~

size = 0

size++ : 일단 0이고 끝나면 나중에 1 더해. 그래서 0번쨰부터 작업할 수 있어\

문자열 비교는 .equals()

- [서울_8반_김민균] Student[] students = new Student[100]; students라는 배열은 student 의 객체가 기본 자료형이고, 그렇게 임의의 class의 객체를 자료형으로 사용 할 수 있군요?
  - 그렇다. class 자체를 자료형이라고 생각하고, 배열을 만들수 있따 배열은 같은 타입의 변수의 모임!

### 클래스 심화

- class의 매개변수를 while문을 통해서 사용자에게 x개 입력받아
- 근데 내가 특정 배열의 개수를 정해놨 그 이상이 들어와
- 그러면 크기 크게, 기존거 복사, 기존거 버려(어떻게?)

#### 가비지 콜렉터

주로 Heap 영역에서 놀고있다,.

Heap영역에 있는 변수를 참조(변수로 할당)하는 곳이 없다? 응 지워~

- 보통 main => UI(User와 직접적인 교류)



### 조회, 입력한 정보가 없을 떄

- 조회 : for문 돌면서 입력된 값과 같은 필드에 있는 정보가 같으면 idx반환
- 근데 기존 idx = -1로 만들어서, -1이면 입력한 정보가 없다고!
- 아니면 그냥 출력해줘!

### 정적 멤버와 static

#### 로딩 시점

- static : 클래스 로딩 시
- non-static : 객체 생성 시(new)



- static : 객체를 생성하지 않아도 존재하는 변수나 함수
  - 클래스의 이름이 처음으로 불릴 때 (클래스 로더가 만들어줌)
- static이 없는 멤버 변수 : 객체로 만들어서 접근해야만 쓸 수 있음
  - 만약 객체로 3개 만들어 ? => 3개의 멤버 변수들 공간이 생겨
    - static : 그냥 혼자 하나 존재해서, 1개의 정적 변수로 존재한다.(열외)



~~~ Java
// Car.java
static int speed;

//CarTest.java
main{
    Car.speed+; // Car라는 클래스를 씀과 동시에 static변수가 메모리에 저장돼
    
    Car car2 = new Car(); // 이렇게해서 접근 가능 spped
    Car2.speed += 1;
    
    Car1.speed
    Car2.speed // ==> 같다!!
}
~~~

cf ) static 전역변수를 만들어서 알고리즘에서 쓸 수도 있음.

~~~ java
Student[] students = new Student[100];
// Student.java 라는 파일이 따로 있음
~~~

 => 내가 만든 임의의 클래스들을 자료형으로 생각해 배열을 만들 수 있따.

### 접근제한자

- 만약 은행계좌에서, public 주인, public 잔고, => 수정 가능.. 헐 .. 
- 왜 private 쓰고, 거기에 접근하는 getter(접근자) 와 setter(설정자) 쓸까?
- 접근제어와 getter + setter 사용하면 좋은점
  - 1. setter를 통해서 값을 검증가능(함수니까, 동작도 수행할 수 있어!)
    2. getter만 작성하면 읽기 전용! => get뭐시기(접근자)
    3. setter만 작성하면 쓰기 전용! => set뭐시기(설정자)
- 보통 자동완성 쓴다. 



- 위쪽 리본 메뉴 - Sourcer - get Getter / Setter

| private     | default     | protected : 잘 안 쓰여                                       | public |
| ----------- | ----------- | ------------------------------------------------------------ | ------ |
| 클래스 내부 | 동일 패키지 | 동일 패키지 + 상속, <br />다른 패키지의 클래스와 <br />상속관계가 있을 경우 접근 가능 | 모두   |

protected : 자식이라면, 어느 패키지에서도 가능



### 싱글턴 패턴

- SW 디자인 패턴. 해당 패턴을을 따르는 클래스는 생성자가 여러 차례 호출, 최초 생성 이후에 호출된 생성잔 최초의 생성자가 생성한 객채를 리턴

- Singleton -> 객채가 1개!!!!!

  ex) new Manager(); new Manager() = 인스턴스 2개씩

  **Manager() => 생성자 호출**

- 기본 생성자에 private을 걸어서 하나만 생성하도록 해!!!!! 

  - 라기보단, Manager 생성자를 외부에서 호출 가능하면 new로 객체 생성 가능,


​			   따라서 private하게 만들어 생성자 자체를 못 쓰게 하자

private Manager () {}

- 6.객체 성성도 안되니, **싱글턴 패턴 내에서 또 private 하게 객체를 생성**해!(like 생성자)

​		private static Manager manager  = new Manager();

getter를 설정해서, pm 객체를 return하게 만들어준다!

​	public static Manager getManager(){

​		return manager} // 위에있는 manager 객체를 return 근데 static해야 그거 가져옴

- 그래서 새롭게 만들려고 하니, 또 새롭게 만들어져 -> static(정적)이 아니여서!
  - 따라서 6.에서도 static을 설정해
- 그런데 getManager에서 return도 필요해, 따라서 이것도 스태틱~
- 따라서 이미 만들어진 객체를 돌려주기만해, 객체 생성은 오직 1번!

### 패키지

- 구분 . 연산자

- com.회사주소.Project_이름(까지가 관레)
- 같은 패키지에 있으면 import 따로 필요 없다
- import ex.*; asterisk : 패키지 바로 밑에 있는 클래스를 가져옴(더 밑은 못 가져옴)
- ex 밑에 또 패키지가 존재하면, 사용할 수 없음,
- 만약 ex 밑에있는 패키지를 실행하고 싶으면 (전체 경로를 설정? )\

### OOP is A PIE

객체 지향 프로그래밍은 abtract 추상화 polumorphism(다형성) Inheritance (상속) Encapsulation(캡슐화)

-> 너무 중요하당!

### 상속(Inheritance)

- 자식클래스 객체 생성은
- 부모 클래스 객체 먼저 선언 후
- 거기에 자식 클래스를 이어 붙여 객체 생성을 완성



~~~java
// 부모 형태
class Parent{
    int data = 10;
    Parent(int data){
        this.data= data; // 이게 기본 생성자이기때문에
        syso("Parent 클래스 생성자")
    }
}
// 자식에서 명시적으로 super(data)를 작성해야함.
// 만약 부모클래스의 기본생성자가있으면 생략 가능(super())
~~~

#### super() => 부모의 (멤버, 메서드)에 직접 접근하기 위해서도 쓸 수 있다(메모리 구조 생각)

- 부모클래스 생성자의 호출, 상속을 받으면 생성자의 첫 줄에서 이 문장을 수행

- 부모클래스의 기본생성자가 없는 경우

  자식클래스 생성자의 첫 줄에서 명시적으로 부모클래스의 생성자를 호출



- 자식클래스의 생성자에서는 제일 처음 부모클래스의 기본생성자를 호출
- 부모클래스의 기본생성자가 없으면 명시적으로 super키워드 => 부모클래스 생성자 호출
- 이것도 this() 생성자와 같이 **생성자** 의 가장 윗 줄에 있어야해!

### 기준 : 메모리를 기준!!!! : 어디 위치에 있는지



### Overiding => 메모리 구조상  가까운것부터 실행하니까~

- 부모가 정의한 변수나 함수를 자식이 똑같이 다시 만드는 것(재정의)
- ) 메소드명, 매개변수, 반환타입-> 다 똑같아야해!!!!!
  - 접근제한이 작아질 순 없다
- super() : 부모의 멤버에 직접 접근하기 위해서도 쓸 수 있다(메모리 구조 생각)



### @Override ( annotation) => 컴파일러에게 검사 의뢰

- 컴파일러가 확인하는 주소

   => 부모 클래스에 있니? 어 있으면 괜찮아, 아님 오류 발생시켜줌!!!

- 조상 클래스(Object) 에 있는 메서드들도 오버라이딩 가능!



#### cf) overloading vs overriding

| overloading                                               | overridng                                                    |
| --------------------------------------------------------- | ------------------------------------------------------------ |
| 생성자, 특정 메서드의 매개변수를 모든 경우의 수 마다 챱챱 | 자식 클래스에서 부모 클래스의 메서드를 재 정의해서 사용하는 것. |



### final

- 한 번 할당받은 값을 더 할당받지 못하도록 제한!
  - 1.변수 : 상수

- 근데 상속이면? (기능이 두 가지 늘어)
  - 2.메소드 오버라이딩 금지 (pubilc final void print(){})
  - 3.상속을 금지 ( final class String)



### 다형성(Polymorphism)

- 많은 형태를 가질 수 있는 성질

#### 중요 : 부모 클래스의 참조변수로 자식 클래스의 객체를 참조할 수 있다

~~~java
Object ob = new Person("해삼", 30); // 가능!, 반대는 불가
~~~

~~~ java
Parent P = new Child();
~~~

- 여기서 만들어질 떄, 일단 Parent의 메모리 먼저 위에 생성,
- 그리고 밑에 Child 메모리 또 붙여서 만들어
- Parent 자료형으로 받았으니까, 가까운 곳에 있는 변수/메소드 
- **Parent로 받았으니까. 자식 멤버 변수는 없다!**

- 메모리에 있는 것과, 사용할 수 있는 것의 차이!!
  - 메모리에 있어도, 참조하는 변수 타입에 따라 접근내용 제한걸림!

#### 활용

-  해삼목록, 멍개목록 ... => 해산물을 상속하니 해산물 배열객체를 만들어 해삼, 멍개의 종류를 담을 수 있다.
- 대신 해산물로 정의했으니까, 해삼에 있는, 멍개에 있는 특성을 쓸 수가 없다는 단점이 있다.

#### 참조형 객체의 형 변환

- 작은곳 -> 큰곳(묵시적 캐스팅)
- 큰곳(Super) 작은집(Son) -> 명시적 캐스팅
  - 무늬만 super인 son
    - Super super = new Super()
    - Son son = (Son)super; => 그냥 아무것도 없어. 걍 super야
      - Son에있는 변수나 메서드 활용 하려고 하면 -> son.makefood
      - ClassCastException
- 조상을 무작정 자손으로 바꿀 수 없어
  - isinstance of 연산자 : 실제 메모리에 있는 객체가 특정 클래스 타입인지 bool로!
  - 



#### 예외 : 동적 바인딩 only 함수

- 상속관계에서, 실제 호출은 자식으로 감
- 변수는 선언한 타입에 가까운 곳에 호출

- 함수가 오버라이딩 돼있으면 자식에서의 함수가 호출된다에요?
  - 맞대!
- 동적 바인딩의 장점
  - toString을 overiding -> 
  - println -> valueof
  - valueof :  Object의 toString의 결과를 내가 받아
  - 그래서 toString을 overiding하면 println도 바껴!!

# 22/01/23

## 실수 모음

- 틀린거, 자동 완성으로 다른 패키지의 같은 이름의 클래스 import -> 틀림
- 기본 접근 제한자가 default -> 다른 패키지에서 접근 불가능
- 입력 받을 떄, 그냥 print로 하자. 개행까지 받아버림
- 질문하자. 내 시간이 아깝다

- private -> getter / setter로만 접근 가능
- 객체의 값을 비교할 땐, equals method 사용
- public static main : 결국 정적 블록, 따라서 static 함수만 불러올 수 있다.
- 조회를 할 땐, 임시로 상태를 이상하게 만들어서(-1), 그 값을 변경하도록, 만약 -1이면 없다고 할 수 있음
- 한 번에 입력받을 생각보단, 지금은 next, next()를 여러번 하는걸 직접 명시해주면 된다.
