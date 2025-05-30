🌱 MySQL 기초 학습 노트
1. 📘 MySQL이란?
관계형 데이터베이스(RDBMS)

데이터를 테이블 형태로 저장

---
2. 🧱 데이터베이스 기본 구조
   
Database > Table > Row(레코드) > Column(속성)

---
3. 🛠️ 자주 쓰는 SQL 문법

3.1 데이터베이스 & 테이블

** 데이터베이스 생성 & 사용
```sql
CREATE DATABASE mydb;
USE mydb;
```
** 테이블 생성
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    age INT
);
```
** 테이블 목록 보기
```sql
SHOW TABLES;
```
** 테이블 구조 보기
```sql
DESCRIBE users;
```
---
3.2 데이터 추가 (INSERT)
```sql
INSERT INTO users (name, age) VALUES ('Alice', 25);
```
3.3 데이터 조회 (SELECT)
```sql
SELECT * FROM users;
SELECT name FROM users WHERE age > 20;
```
3.4 데이터 수정 (UPDATE)
```sql
UPDATE users SET age = 26 WHERE name = 'Alice';
```
3.5 데이터 삭제 (DELETE)
```sql
DELETE FROM users WHERE name = 'Alice';
```
---
4. 🔍 WHERE 조건문
** 비교 연산자
=, !=, <, >, <=, >=

** 논리 연산자
AND, OR, NOT

** 기타 조건
```sql
BETWEEN 10 AND 20
LIKE '%ice'  -- 패턴 일치
IN ('Alice', 'Bob')
```
---
5. 📊 정렬, 그룹화

** 정렬
```sql
SELECT * FROM users ORDER BY age DESC;
```
** 그룹화
```sql
SELECT age, COUNT(*) FROM users GROUP BY age;
```
-- 조건 있는 그룹화
```sql
HAVING COUNT(*) >= 2;
```
---
6. 🔗 테이블 JOIN (기본)

** INNER JOIN 예시
```sql
SELECT *FROM users uJOIN orders o ON u.id = o.user_id;
```
---
7. ✨ 기타 유용한 문법

** 이름
```sql
SELECT name AS 사용자이름 FROM users;
```
** 중복 제거
```sql
SELECT DISTINCT age FROM users;
```
** LIMIT (결과 수 제한)
```sql
SELECT * FROM users LIMIT 5;
```
