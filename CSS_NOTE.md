## CSS란?
CSS는 웹페이지를 예쁘게 꾸미는 도구.

HTML이 웹사이트의 뼈대라면, CSS는 옷, 화장, 인테리어라고 할 수 있다.

** 예를 들어:

** HTML이 "버튼"을 생성하고->CSS는 버튼에 색깔,크기,그림자등을 덮어준다.

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

