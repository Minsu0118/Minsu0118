## CSS란?
* CSS는 웹페이지를 예쁘게 꾸미는 도구.
* HTML이 웹사이트의 뼈대라면, CSS는 옷, 화장, 인테리어라고 할 수 있다.

---
## CSS가 해주는 일(5가지)
* 글자 크기, 색상, 간격 조절
* 배경색, 이미지 추가
* 버튼/박스에 테두리, 그림자 적용
* 요소를 가로/세로로 배치
* 모바일, 태블릿, 데스크 탑에 맞게 디자인 다르게 보이게 하기(반응형 웹)

---

## HTML + CSS
```css
<!DOCTYPE html>
<html>
<head>
  <style>
    h1 {
      color: blue;
      font-size: 36px;
      text-align: center;
    }
    p {
      color: gray;
      font-family: 'Arial';
    }
  </style>
</head>
<body>
  <h1>안녕하세요!</h1>
  <p>이건 CSS로 꾸민 웹페이지입니다.</p>
</body>
</html>
```
---
## ✨ CSS 적용 방법 3가지
* 인라인 스타일: 태그에 직접 스타일을 씀
```
  <p style="color:red;">빨간 글씨</p>
```
* 내부 스타일: <style> 태그 안에 작성

* 외부 스타일시트: .css 파일로 따로 작성
```css
 <link rel="stylesheet" href="style.css">
```

## 활용예제_자기소개
```css
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>CSS 활용 예제</title>
  <style>
    /* 전체 배경/ 기본 폰트 설정 */
    body {
      background-color: #f0f4f8;
      font-family: "Segoe UI", sans-serif;
      margin: 0;
      padding: 0;
    }

    /* 상단 헤더 스타일 */
    header {
      background-color: #e598e6;
      color: white;
      padding: 18px;
      text-align: center;
    }

    /* 섹션 박스 스타일 */
    .container {
      max-width: 620px;
      margin: 30px auto;
      background-color: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    h2 {
      color: 9e9;
    }

    p {
      line-height: 1.7;
    }

    /* 버튼 스타일 */
    .btn {
      background-color: #007acc;
      color: white;
      padding: 12px 20px;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .btn:hover {
      background-color: #005fa3;
    }
  </style>
</head>
<body>

  <!-- 헤더 영역 -->
  <header>
    <h1>자기 소개</h1>
  </header>

  <!-- 본문 영역 -->
  <div class="container">
    <h2>안녕하세요!</h2>
    <p>더 나은 코드와 구조를 고민하며, 효율적이고 안정적인 서비스를 만드는 개발자입니다. 기술적 성장과 협업을 통해 함께 성장하는 개발 문화를 지향합니다. 사용자 경험을 최우선으로 생각하며, 가치 있는 서비스를 만드는 데 집중합니다.</p>
  </div>

</body>
</html>

```
