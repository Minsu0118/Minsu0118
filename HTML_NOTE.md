## 🌐 HTML이란?

HTML은 우리가 웹사이트를 만들 때 뼈대를 만드는 재료입니다.
예를 들어, 건물을 지을 때 기둥과 벽이 필요하듯, 웹 페이지에도 그런 구조가 필요합니다.
그 구조를 짜는 게 바로 HTML의 역활입니다.

---
## 🧱 HTML의 주요기능은 주로 3가지로 나눌 수 있습니다.

* 화면에 제목, 글, 사진, 버튼 등의 시각화
* 정보를 구역별로 나누고 정리
* 웹사이트가 어떤 내용인지 검색엔진이나 브라우저가 이해할 수 있게 도움

---
## 📦 기본적인 HTML 모습
```html
<!DOCTYPE html>
<html>
  <head>
    <title>내 웹페이지</title>
  </head>
  <body>
    <h1>안녕하세요!</h1>
    <p>My Name is minsuPark</p>
  </body>
</html>
```

---
## 자주 쓰는 HTML 태그

* `<태그>` - 하는 일  
  * `<h1>` - 큰 제목  
  * `<p>` - 문단, 일반 글  
  * `<a>` - 다른 페이지 이동 링크  
  * `<img>` - 이미지 보여주기  
  * `<button>` - 버튼 생성  
  * `<div>` - 영역 나누기  
  * `<input>` - 사용자에게 정보 받기
 
  ## 활용예제_자기소개
```html
  <!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>202103738 박민수</title>
  <style>
    body {
      font-family: sans-serif;
      margin: 28px;
    }
    h1 {
      color: #e598e6c;
    }
    img {
      width: 100px;
      border-radius: 50%;
    }
    .section {
      margin-bottom: 28px;
    }
  </style>
</head>
<body>

  <!-- 제목 -->
  <h1>안녕하세요 소프트웨어 공학과 박민수입니다.</h1>

  <!-- 이미지 -->
  <div class="section">
    <img src="위치/파일명 또는 파일 주소소" alt="프로필">
  </div>

  <!-- 자기소개 -->
  <div class="section">
    <h2>자기소개</h2>
    <p>웹 개발을 공부 중이며, HTML과 CSS, JavaScript에 관심이 많습니다.</p>
  </div>

  <!-- 링크 -->
  <div class="section">
    <h2>포트폴리오</h2>
    <a href="https://example.com" target="_blank">제 포트폴리오 보기</a>
  </div>

  <!-- 목록 -->
  <div class="section">
    <h2>좋아하는 기술</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </div>

  <!-- 폼 -->
  <div class="section">
    <h2>연락하기</h2>
    <form action="/send" method="post">
      <input type="text" name="name" placeholder="이름"><br><br>
      <input type="email" name="email" placeholder="이메일"><br><br>
      <textarea name="message" placeholder="메시지" rows="5" cols="30"></textarea><br><br>
      <input type="submit" value="보내기">
    </form>
  </div>

</body>
</html>
```
