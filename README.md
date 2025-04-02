## 백엔드 개발자 박민수

> 더 나은 코드, 더 나은 경험, 더 나은 개발자가 되기 위해 끊임없이 성장합니다
---





* 서일대학교(재학중2025)
* 대경상업고등학교(졸업2021)

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
