## 백엔드 개발자 박민수

> 더 나은 코드, 더 나은 경험, 더 나은 개발자가 되기 위해 끊임없이 성장합니다
---





* 서일대학교(재학중)
* 대경상업고등학교(졸업)

---
### Skill

* Front-end
  * **HTML (8)**
  * **CSS (8)**
  * **JAVA Script (7)**
* Back-end
  * **JAVA (7.5)**
  * **C# (7.5)**
* Data
  * **My SQL (7.5)**

 ---
 ### 자격증
 * 컴퓨터 활용 능력 1급(예정)

 ---
 ### 학업 성과 및 수상


 ---
 ### 프로젝트
 * AI 챗봇(GOOD RECIPE)
 * ![GOOD Recipe](https://github.com/Minsu0118/Minsu0118/blob/main/GOOD%20RECIPE.png)
   * 사용자가 쉽고 빠르게, 가지고 있는 재료들을 주제로 만들 수 있는 요리의 레시피 추천 어플리케이션
   * <https://cdn.botpress.cloud/webchat/v2.3/shareable.html?configUrl=https://files.bpcontent.cloud/2024/12/03/05/20241203054619-IWT367AD.json>


 * 의약품 AI 서비스(약숲터)
   * 복용자의 약의 성분을 빠르게 알고 그에 맞는 영양제 추천 서비스 어플리케이션
 ---
 ### 온라인 강의
 * 이젠 강의(프로그래밍)
### 오프라인 프로그램
 * 대우 국비 지원 프로그램_웹 클라우드 (보안)코딩

------------------------------
### 학습노트
#### HTML
1. ![기본 Form 구성](https://github.com/Minsu0118/Minsu0118/blob/main/SmartSelect_20250326-122112_ChatGPT.jpg)

2. 상황 별 태그
   * 제목 태그: h1 ~ h6 (크기가 점점 작아짐)

   * 문단 태그: p

   * 링크 태그: a href="URL"텍스트/a

   * 이미지 태그: img src="이미지경로" alt="설명"

   * 목록 태그:

     * 순서 없는 목록: ul li항목/li /ul

     * 순서 있는 목록: //ol li항목/li /ol

     * 표 태그: table, tr, td, th

---
#### JAVA
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
   * public int add(int a, int b) {


      return ;
     }

5. 제어문
import java.util.Iterator;

public class Ex08_01 {
/* 08장/제어문을 보조하는 보조 제어문.pdf No.13 1번 문제
 * 1부터 100사이의 자연수중에서 제일 큰 7의 배수를 구하
 * 는 프로그램을 작성하시오.  (Ex08_01.java-> for,if,%등)
 * 단, 100부터 1까지 1씩 감소하면서 반복하지 말고 1부터 100까지 반복해서 구한다.
 * */
	public static void main(String[] args) {
		//답안 코드
		int max =0;
		
		for (int i=1;i<=100;i++) {
			if(i %7 ==0) {
				max = i;
			}
		}System.out.println("제일 큰 7의 배수: "+ max);
		
		System.out.println("===============\n");
		
		
		for (int i=100;i>=1;i--) {
			if(i %7 ==0) {
				break;
			}
		}System.out.println("제일 큰 7의 배수: "+ max);
		
		System.out.println("===============\n");
	
		int sevenMax = 0;
		int n;
		for(n=1;n<=100;n++) {
			if(n %7 == 0) {
				sevenMax = n;
			}
		}
		System.out.printf("7의 배수중 가장 큰 값=%d\n", sevenMax);
		
		System.out.println("===============\n");
		
		/* 2번 문제) 100부터 1까지 1씩 감소하면서 for 반복운동을 활용하여 6의
		 * 배수중 최대값을 구하는 코드를 만들어 보자.
		 * */
		//답안코드
		int m;
		
		for (m = 100; m >= 1; m--) {
			if(m %6 == 0) {
				break;
			}
		}System.out.println("6의 배수 중 최대값:"+m);
		
	}

}

7. 배열 문법_기본
* public class ArrayEx01 {
/*
 * 배영이라 동일한 타입의 하나 이상 복수개의 원소값을 고정된 추가로 한꺼번에
 * 저장하기 위해서 사용하는 것울 말한다.
 * new 키워드를 사용한 배열 생성법)
 * 타입[] 배열명 = new 타입[배열크기)*/
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

}



     }
 


<!--
**Minsu0118/Minsu0118** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
