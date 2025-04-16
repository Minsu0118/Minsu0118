1. 🌱 기본 구조
csharp
복사
편집
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Hello, World!");
    }
}
2. 📦 변수 & 자료형
csharp
복사
편집
int age = 25;
string name = "Alice";
bool isActive = true;
double height = 172.5;
3. 🧠 조건문 & 반복문
csharp
복사
편집
// if문
if (age > 20) { Console.WriteLine("성인"); }

// switch문
switch (age)
{
    case 20: Console.WriteLine("스무살"); break;
    default: Console.WriteLine("다른 나이"); break;
}

// for문
for (int i = 0; i < 5; i++) { Console.WriteLine(i); }

// while문
while (age < 30) { age++; }
4. 📦 배열 & 리스트
csharp
복사
편집
int[] nums = { 1, 2, 3 };
List<string> names = new List<string> { "Tom", "Sue" };
5. ⚙️ 메서드 (함수)
csharp
복사
편집
static int Add(int a, int b)
{
    return a + b;
}
6. 🧱 클래스 & 객체
csharp
복사
편집
class Person
{
    public string Name;
    public int Age;

    public void SayHello()
    {
        Console.WriteLine("Hi, I'm " + Name);
    }
}

// 객체 생성
Person p = new Person();
p.Name = "Alice";
p.Age = 30;
p.SayHello();
7. 🧰 기타 유용한 문법
csharp
복사
편집
// null 체크
string? msg = null;
if (msg != null) Console.WriteLine(msg);

// 문자열 보간
string name = "Bob";
Console.WriteLine($"Hello, {name}");

// try-catch 예외 처리
try {
    int x = 10 / 0;
}
catch (Exception e) {
    Console.WriteLine("에러: " + e.Message);
}
