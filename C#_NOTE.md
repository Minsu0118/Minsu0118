1. 🌱 기본 구조
```c#
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Hello, World!");
    }
}
```
---
2. 📦 변수 & 자료형
```c#
int age = 24;
string name = "minsu";
bool isActive = true;
double height = 168.0;
```
---
3. 🧠 조건문 & 반복문
```c#
// if문
if (age > 20) { Console.WriteLine("성인"); }
```
```c#
// switch문
switch (age)
{
    case 20: Console.WriteLine("스물"); break;
    default: Console.WriteLine("다른 나이"); break;
}
```
```c#
// for문
for (int i = 0; i < 5; i++) { Console.WriteLine(i); }
```
```c#
// while문
while (age < 30) { age++; }
```
---
4. 📦 배열 & 리스트
```c#
int[] nums = { 1, 2, 3 };
List<string> names = new List<string> { "Ring", "Su" };
```
---
5. ⚙️ 메서드 (함수)
```c#
static int Add(int a, int b)
{
    return a + b;
}
```
---
6. 🧱 클래스 & 객체
```c#
class Person
{
    public string Name;
    public int Age;

    public void SayHello()
    {
        Console.WriteLine("HELLO, I'm " + Name);
    }
}

// 객체 생성
Person p = new Person();
p.Name = "Alice";
p.Age = 24;
p.SayHello();
```
---
7. 🧰 기타 유용한 문법
```c#
// null 체크
string? msg = null;
if (msg != null) Console.WriteLine(msg);

// 문자열 보간
string name = "minsu";
Console.WriteLine($"Hello, {name}");

// try-catch 예외 처리
try {
    int x = 20 / 0;
}
catch (Exception e) {
    Console.WriteLine("에러: " + e.Message);
}
```
