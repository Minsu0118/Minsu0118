
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

5. 반복문
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


6.조건문
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

   


7. 제어문
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

9. 배열 문법_기본

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

10.메소드
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
