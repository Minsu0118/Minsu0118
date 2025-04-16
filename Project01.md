`` Good Recipe ``

* Demo버전 <https://cdn.botpress.cloud/webchat/v2.3/shareable.html?configUrl=https://files.bpcontent.cloud/2024/12/03/05/20241203054619-IWT367AD.json>
     
--- 
## 📱 프로젝트 개요
* 프로젝트명: Good Recipe
* 개발 기간: 2024.09 ~ 2024.11
* 역할: 개인 프로젝트 (기획, 설계, 개발 100%)
* 목표: 사용자 편의를 위해 가지고 있는 재료를 기반으로 간단히 만들 수 있는 요리를 추천해주는 챗봇 개발

## 🧠 Botpress 기반 요리 레시피 추천 챗봇
* 사용자가 입력한 가지고 있는 재료를 기반으로 만들 수 있는 요리 레시피를 추천해주는 AI 챗봇 앱입니다.
* Botpress로 챗봇 인터페이스를 구축하고, Android Studio로 UI를 구성하여 간단하고 직관적인 사용자 경험을 제공하도록 설계했습니다.

## 🧩 주요 기능
기능	설명
* 재료 입력	사용자가 가지고 있는 재료를 ai챗봇의 질문목록에서 선택
* 요리 추천	입력된 재료를 기반으로 가능한 요리 목록 추천
* 레시피 제공	조리 방법, 필요한 추가 재료, 시간 등 상세 정보 제공

## 🛠️ 기술 스택
* 챗봇 엔진	Botpress (v12.x)
* 자연어 처리	Botpress NLU + 외부 API (옵션: OpenAI, Spoonacular 등)
* 백엔드	Firebase (Authentication, Firestore)
* 디자인	Figma (UI 와이어프레임 및 프로토타이핑)

## 🤖 Botpress Flow 구성
1. ai 챗봇질문 목록(고기, 야채, 생선, 아침, 점심, 저녁....)
2. 사용자 재료 입력
3. 요리 추천 (재료 기반 필터링)
4. 상세 레시피 보기
5. 추가 질문(칼로리, 요리 시간....)/ 종료

## 📷 UI 화면 예시
* 메인 화면
     * ![GOOD Recipe](./GOOD%20RECIPE.png)
* 추천 리스트 화면
     * ![추천 창](https://./botpress_select.PNG)
* 레시피 상세 팝업
     * ![기타 선택](https://./botpress_another.PNG)

## 💡 구현 중 어려웠던 점
* 재료 조합 다양성: 비슷한 재료로 인한 입력 오류/ 데이터 수집
* 대화 흐름 UX: 사용자의 반복 질문/오류 입력을 자연스럽게 처리하도록 Retry Flow 구성

## 📈 향후 계획
* 카메라로 재료 인식 (OCR, 이미지 분석)
* 사용자 알러지 및 음식 취향 프로필 저장
* GPT 기반 레시피 요약 기능
* App Store / Google Play 등록
