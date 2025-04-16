1. 🚀 기본 문법
javascript
복사
편집
let name = "Alice";     // 변수 선언 (변경 가능)
const age = 25;         // 상수 선언 (변경 불가)

console.log(name);      // 출력
2. 🔁 조건문 & 반복문
javascript
복사
편집
if (age > 20) {
  console.log("성인");
} else {
  console.log("미성년자");
}

for (let i = 0; i < 3; i++) {
  console.log(i);
}

while (age < 30) {
  age++;
}
3. 🧠 함수
javascript
복사
편집
function greet(name) {
  return "Hello, " + name;
}

const sayHi = (name) => `Hi, ${name}`;  // 화살표 함수
4. 📦 배열 & 객체
javascript
복사
편집
let fruits = ["apple", "banana"];
fruits.push("orange");

let person = {
  name: "Tom",
  age: 30
};
console.log(person.name);
5. 📄 DOM 조작
javascript
복사
편집
// 요소 선택
const btn = document.querySelector("#myBtn");

// 이벤트 처리
btn.addEventListener("click", () => {
  alert("버튼 클릭됨!");
});

// 텍스트 변경
document.querySelector("#title").textContent = "변경된 제목";
6. 🧪 조건 짧게 쓰기
javascript
복사
편집
let msg = age >= 20 ? "성인" : "미성년자";  // 삼항 연산자
let userName = name || "Guest";            // null 대체
7. 📬 비동기 처리 (fetch)
javascript
복사
편집
fetch("https://api.example.com/data")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
8. ✨ 기타 유용 문법
javascript
복사
편집
// 구조 분해
const { name, age } = person;

// 템플릿 문자열
console.log(`이름: ${name}, 나이: ${age}`);

// 배열 반복
fruits.forEach(f => console.log(f));

// map
let lengths = fruits.map(f => f.length);
💡 프론트엔드 개발 흐름
HTML: 뼈대

CSS: 스타일

JS: 동작 제어 (이벤트, DOM 조작, 서버 통신 등)

