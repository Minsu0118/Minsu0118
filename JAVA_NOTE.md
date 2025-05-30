
#### JAVA
1. ![기본 Form 구성](https://github.com/Minsu0118/Minsu0118/blob/main/%EA%B8%B0%EB%B3%B8%20%EC%9E%90%EB%B0%94.PNG)
1. Java 개요
* JVM 기반, 플랫폼 독립적
* 객체지향 프로그래밍(OOP) 지원
* 자동 메모리 관리(GC)
2. 기본 문법
  * 기본 : int, long, short, boolean
  * 참조 : String 등
  * 제어 : if, switch, for, while
3. OOP 개념
 * 캡슐화, 상속성, 다형성, 추상화
4. 기본 메서드 구성
```JAVA
* public int add(int a, int b) {


return ;
}
```

## 반복문
   (for, while, do-while)

(for)
```java
for (int i = 0; i < 8; i++) {
    System.out.println("현재 i의 값: " + i);
}
```

(while)
```java
int i = 0;
while (i < 4) {
    System.out.println("현재 i의 값: " + i);
    i++;  // i 값을 1씩 증가시킴
}
```

(do-while)
```java
int i = 0;
do {
    System.out.println("현재 i의 값: " + i);
    i++;  // i 값을 1씩 증가시킴
} while (i < 3);
```


## 조건문
   (if, else if, switch)

(if)
```java
age = 24
if age >= 24:
    print("당신은 성인입니다.")
```

(if else)
```java
int score = 96;

if (score >= 90) {
    System.out.println("A 학점");
} else if (score >= 80) {
    System.out.println("B 학점");
} else {
    System.out.println("C 학점 이하");
}
```

(switch)
```java
int day = 3;
String dayName;

switch (day) {
    case 1:
        dayName = "월요일";
        break;
    case 2:
        dayName = "화요일";
        break;
    case 3:
        dayName = "수요일";
        break;
    case 4:
        dayName = "목요일";
        break;
    case 5:
        dayName = "금요일";
        break;
    case 6:
        dayName = "토요일";
        break;
    case 7:
        dayName = "일요일";
        break;
    default:
        dayName = "잘못된 입력";
        break;
}

System.out.println(dayName);  // "요일" 출력
```

   


## 제어문
```java
public class Multiples {
    public static void main(String[] args) {
        int max = 0; // 가장 큰 7의 배수를 저장할 변수

        // 1부터 100까지 반복하면서 7의 배수를 찾음
        for (int i = 1; i <= 100; i++) {
            if (i % 7 == 0) { // 7의 배수인지 확인
                max = i; // 가장 마지막으로 찾은 7의 배수가 최대값이 됨
            }
        }
        System.out.println("제일 큰 7의 배수: " + max);
        System.out.println("===============\n");

        // 100부터 1까지 감소하면서 7의 배수를 찾음
        for (int i = 100; i >= 1; i--) {
            if (i % 7 == 0) { // 7의 배수인지 확인
                max = i; // 첫 번째로 찾은 7의 배수가 최대값이 됨
                break; // 찾았으면 반복문 종료
            }
        }
        System.out.println("제일 큰 7의 배수: " + max);
        System.out.println("===============\n");

        int sevenMax = 0; // 7의 배수 중 최대값을 저장할 변수
        int n;

        // 1부터 100까지 반복하면서 7의 배수를 찾음
        for (n = 1; n <= 100; n++) {
            if (n % 7 == 0) { // 7의 배수인지 확인
                sevenMax = n; // 가장 마지막으로 찾은 7의 배수가 최대값이 됨
            }
        }
        System.out.printf("7의 배수 중 가장 큰 값=%d\n", sevenMax);
        System.out.println("===============\n");

        /*
         * 2번 문제) 100부터 1까지 1씩 감소하면서 for 반복문을 활용하여
         * 6의 배수 중 최대값을 구하는 코드를 만들어 보자.
         */
        
        int m;

        // 100부터 1까지 감소하면서 6의 배수를 찾음
        for (m = 100; m >= 1; m--) {
            if (m % 6 == 0) { // 6의 배수인지 확인
                break; // 첫 번째로 찾은 6의 배수가 최대값이므로 반복문 종료
            }
        }
        System.out.println("6의 배수 중 최대값: " + m);
    }
}
```

## 배열 문법_기본
```java
/*배열이란 동일한 타입의 하나 이상 복수개의 원소값을 고정된 추가로 한꺼번에
   저장하기 위해서 사용하는 것울 말한다.
   new 키워드를 사용한 배열 생성법)
   타입[] 배열명 = new 타입[배열크기)*/
   
 public class ArrayEx01 {
	public static void main(String[] args) {
		int[] score = new int[5];
		score[0]=100;//배열 주소 인덱스 번호는 1이 아닌 0부터 시작하는 것에 조심하길 바란다.
		score[1]=90;//2번째 배열원소값으로 90을 저장
		score[2]=99;
		score[3]=80;
		score[4]=97;

		System.out.printf("배열 크기=%d\n", score.length);//배열 크기 인 배열원소개수는
		//배열명.length로 반환한다.
		
		//일반 for 반복문으로 배열원소값을 일괄적으로 출력
		for(int i = 0; i<score.length; i++) {//배열주소 인덱스번호는 0부터 시작하니
			//반복문 제어변수 초기값도 0으로 함..
			System.out.println("score["+i+"] = "+ score[i]);
		}
	}
```
## 다차원 배열
기본)
int [][]score = new int [5][3];

예제)
```java
public class Arr03 { 
public static void main(String[] args) { 
//정수값을 담을 수 있는 5행 3열짜리 기억공간이 생성
int [][]score=new int [5][3]; 
int row, col; //반복문에서사용할제어변수선언
//행과 열의 위치를 첨자로 지정하여 값 대입
score[0][0]=10; score[0][1]=90; score[0][2]=70; 
score[1][0]=60; score[1][1]=80; score[1][2]=65; 
score[2][0]=55; score[2][1]=60; score[2][2]=85; 
score[3][0]=90; score[3][1]=75; score[3][2]=95; 
score[4][0]=60; score[4][1]=30; score[4][2]=80; 

///반복문으로 일괄처리
for(row = 0; row < 5 ; row++){ 
 for(col = 0; col < 3 ; col++) 
   System.out.print(" " +score[row][col]); 
 System.out.println(""); //행단위로 줄 바
	} 
    } 
}
```

## 메소드
특정 작업을 수행하는 코드 블록입니다. 자주 사용되는 코드들을 묶어두고, 필요할 때마다 호출하여 재사용할 수 있게 도와주는 기능

```java
반환타입 메소드이름(매개변수) {
    // 메소드가 수행할 작업
    // return 반환값;
}
```


예제)
```java
public class Main {
    public static void printDetails(String name, int age) {
        System.out.println("이름: " + name);
        System.out.println("나이: " + age);
    }

    public static void main(String[] args) {
        printDetails("박민수", 24);  // printDetails 메소드 호출
    }
}
```

## 메소드 오버 로딩
```java
public class MethodTest01{ 
	public static void main(String[] args) { 
	//(1) 논리값 : true, false 
	System.out.println(true); 
	//(2) 문자 : 단일 따옴표로 묶어줌
	System.out.println('A'); 
	//(3) 정수 : 소수점이 없는 수
	System.out.println(128); 
	//(4) 실수 : 소수점이 있는 수
	System.out.println(3.5); 
	//(5) 문자열 : 이중 따옴표로 묶어줌
	System.out.println("Hello"); 
	} 
}
```

예제)
전달인자 자료형이 다른 메소드 오버로딩
```java
public class MethodTest02{ 
//int형 데이터에대해서절대값을구하는메소드정의
int abs(int num){
if(num<0)

 num=-num;
return num;

//long형 데이터에 대해서 절대값을 구하는 메소드 정의
long abs(long num){
if(num<0)

 num=-num;
return num;
}
//double 데이터에 대해서 절대값을 구하는 메소드 정의
double abs(double num){
if(num<0) 
 num=-num; 
return num; 
}

public static void main(String[] args) { 
MethodTest02 mt=new MethodTest02(); 
 
//전달인자가 int형 이므로 03:의 int형 데이터에 대해서 절대값을 구하는 메소드 호출
int var01=-10, var02; 
var02=mt.abs(var01); 
System.out.println(var01 + "의 절대값은-> " + var02); 

//전달인자가 long형이므로 09:의 long형 데이터에 대해서 절대값을 구하는 메소드 호출
long var03=-20L, var04; 
var04=mt.abs(var03); 
System.out.println(var03 + "의 절대값은-> " + var04); 
 
//전달인자가 double형이므로 15:의 double형에 대해서 절대값을 구하는 메소드 호출
double var05=-3.4, var06; 
var06=mt.abs(var05); 
System.out.println(var05 + "의 절대값은-> " + var06); 
} 
} 
```

## 생성자
1.생성자 이름 = 클래스 이름. new 클래스명();에 의해서 생성자 호출

2.생성자의 주된 기능은 클래스 소속 멤버 변수중 인스턴스 변수 초기화 기능.

3.생성자명 앞에 리턴타입은 정의하지 않는다.

```java
class MyDate21{
	private int year;//년도값
	private int month;//월값
	private int day;//일값, 3개의 속성정의(클래스 소속의 멤버변수 중 인스턴스 변수가 된다.)
	
	public MyDate21() {//전달 인자가 없는 기본 생성자 정의
		year=2025; month=4; day=7;//생성자의 주된 기능인 인스턴스 변수 초기화 기능.
		System.out.println("기본생성자 호출");
	}
	
	public void pr() {
		System.out.println(year+"년 " +month+"월 " +day+"일");
	}
}

public class ConsEx01 {

	public static void main(String[] args) {
		MyDate21 d =new MyDate21();//new 클래스명();에 의해서 10번 줄 기본생성자 호출
		d.pr();//객체명.메서드()에 의해서 해당 메서드를 호출해서 초기화 한 인스턴스 변수값 출력
	}

}
```

예제)
```java
class Member02{
	private String mem_id;//회원 아이디
	private String mem_name;//회원 이름
	private String mem_addr;//회원주소->3개의 클래스 소속 멤버변수(속성) 정의
	
	public Member02() {//전달인자가 없는 생성자를 기본생성자라 한다. 기본 생성자는
	//default(디폴트) 생성자이다. 생성자가 오버로딩이 안 되어 있을때는 자바 컴파일러가
	//기본생성자를 묵시적 저공한다.
		mem_id="kkkk"; mem_name="홀길동"; mem_addr="서울기 중랑구";//생성자릐 주된 기능인 멤버변수 초기화
		
	}
	public Member02(String new_id, String new_name, String new_addr) {
		mem_id=new_id; mem_name=new_name; mem_addr=new_addr;//생성자의 주된 기능인 멤버변수 초기화
	}//전달인자 개수가 다른 생성자 오버로딩

	public void print() {
		System.out.println("회원 아이디:"+mem_id+", 회원 이름:"+mem_name+", 회원 주소:"+mem_addr);
	}//사용자 정의 메서드 정의=>초기화 된 멤버변수 값을 출력하는 기능을 가진다.
}

public class ConsEx02 {

	public static void main(String[] args) {
		Member02 member=new Member02();//new Member02();에 의해서 전달인자가 없는 기본생성자를 호출
		member.print();
		
		Member02 member2=new Member02("aaaaa", "이순신", "서울시 동대문구");//전달인자 3개짜리 오버로딩 된 생성자 호출
		member2.print();//member와 member2는 서로 다른 객체주소를 가진다.

	}

}
```
