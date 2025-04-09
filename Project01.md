---
 ## 프로젝트
 * AI 챗봇(GOOD RECIPE)
 * ![GOOD Recipe](https://github.com/Minsu0118/Minsu0118/blob/main/GOOD%20RECIPE.png)
   * 사용자가 쉽고 빠르게, 가지고 있는 재료들을 주제로 만들 수 있는 요리의 레시피 추천 어플리케이션
   * Demo버전 <https://cdn.botpress.cloud/webchat/v2.3/shareable.html?configUrl=https://files.bpcontent.cloud/2024/12/03/05/20241203054619-IWT367AD.json>
     
--- 

## 🧠 Botpress 기반 요리 레시피 추천 챗봇
사용자가 입력한 가지고 있는 재료를 기반으로 만들 수 있는 요리 레시피를 추천해주는 AI 챗봇 앱입니다.
Botpress로 챗봇 인터페이스를 구축하고, Android Studio로 UI를 구성하여 간단하고 직관적인 사용자 경험을 제공하도록 설계했습니다.

## 📱 프로젝트 개요
프로젝트명: Good Recipe

개발 기간: 2025.03 ~ 2025.04

역할: 개인 프로젝트 (기획, 설계, 개발 100%)

목표: 사용자 편의를 위해 냉장고 속 재료로 만들 수 있는 요리를 추천해주는 챗봇 개발

🧩 주요 기능
기능	설명
재료 입력	사용자가 가지고 있는 재료를 자연어로 입력
요리 추천	입력된 재료를 기반으로 가능한 요리 목록 추천
레시피 제공	조리 방법, 필요한 추가 재료, 시간 등 상세 정보 제공
즐겨찾기	자주 보는 레시피 저장 가능 (Firebase 연동 예정)
확장 준비	알러지 필터링, 칼로리 필터링, 이미지 인식 등 확장 고려 중
🛠️ 기술 스택
영역	기술
챗봇 엔진	Botpress (v12.x)
자연어 처리	Botpress NLU + 외부 API (옵션: OpenAI, Spoonacular 등)
모바일 앱	Android Studio (Kotlin)
백엔드	Firebase (Authentication, Firestore)
디자인	Figma (UI 와이어프레임 및 프로토타이핑)
🤖 Botpress Flow 구성
markdown
복사
편집
Start
  └─ 사용자 재료 입력
        └─ 요리 추천 (재료 기반 필터링)
              └─ 상세 레시피 보기
                    └─ 추가 질문 / 저장 / 종료
Slots: ingredients, selected_recipe

Custom Action: GetRecipesFromIngredients.ts

QnA 처리: 다양한 재료 조합 질문을 처리할 수 있도록 Botpress QnA 모듈 활용

📷 UI 화면 예시 (원하는 경우 이미지 첨부)
재료 입력 화면

추천 리스트 화면

레시피 상세 팝업

저장된 레시피 보기 화면

💡 구현 중 어려웠던 점 & 해결 방법
재료 조합 다양성: 단어 유사도 기반 필터링으로 해결 (예: "달걀" vs "계란")

Botpress 외부 API 연동: axios를 활용하여 레시피 API 호출

대화 흐름 UX: 사용자의 반복 질문/오류 입력을 자연스럽게 처리하도록 Retry Flow 구성

📈 향후 계획
카메라로 재료 인식 (OCR, 이미지 분석)

사용자 알러지 및 음식 취향 프로필 저장

GPT 기반 레시피 요약 기능

App Store / Google Play 등록
