<p>$\large{\rm{\color{#5ad7b7}PCEat(피씨잇)}}$</p> PC방 푸드 포인트 웹 사이트

# 프로젝트 개요
  * PC방 이용 고객을 위한 음식 주문 포인트 적립 웹서비스 개발을 목표로 합니다.
  * 고객이 음식을 주문할 때마다 포인트를 자동으로 적립하고, 적립된 포인트를 할인이나 이벤트 참여 등에 사용할 수 있도록 하여, 이용자의 만족도 향상과 점포 매출 증대를 기대합니다.



# DB 구성
<img src="./PC_DB.png" alt="PCEat DB" width="700" height="300"/>

1. 유저 테이블

```db
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY COMMENT '유저 고유 ID',
  username VARCHAR(100) NOT NULL COMMENT '유저 이름',
  password VARCHAR(100) NOT NULL COMMENT '비밀번호',
  total_points INT DEFAULT 0 COMMENT '누적 포인트',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP COMMENT '가입일시'
) COMMENT='유저 정보';
```

```db
2. 메뉴(상품) 테이블
CREATE TABLE menus (
  id INT AUTO_INCREMENT PRIMARY KEY COMMENT '메뉴 고유 ID',
  name VARCHAR(100) NOT NULL COMMENT '상품 이름',
  price INT NOT NULL COMMENT '가격',
  image_url VARCHAR(255) COMMENT '이미지 파일 경로',
  category VARCHAR(50) COMMENT '분류 (밥, 면, 분식, 음료 등)'
) COMMENT='상품(메뉴) 정보';
```

```db
3. 장바구니 테이블
CREATE TABLE carts (
  id INT AUTO_INCREMENT PRIMARY KEY COMMENT '장바구니 항목 ID',
  user_id INT NOT NULL COMMENT '유저 ID',
  menu_id INT NOT NULL COMMENT '상품 ID',
  quantity INT NOT NULL COMMENT '수량',
  FOREIGN KEY (user_id) REFERENCES users(id),
  FOREIGN KEY (menu_id) REFERENCES menus(id)
) COMMENT='장바구니';
```

```db
4. 주문 테이블
CREATE TABLE orders (
  id INT AUTO_INCREMENT PRIMARY KEY COMMENT '주문 ID',
  user_id INT NOT NULL COMMENT '주문자 유저 ID',
  total_price INT NOT NULL COMMENT '총 결제금액',
  payment_method VARCHAR(50) COMMENT '결제 수단 (현금, 카드, 포인트)',
  paid BOOLEAN DEFAULT FALSE COMMENT '결제 완료 여부',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP COMMENT '주문 시각',
  FOREIGN KEY (user_id) REFERENCES users(id)
) COMMENT='주문 내역';
```

```db
5. 주문 상세 테이블
CREATE TABLE order_items (
  id INT AUTO_INCREMENT PRIMARY KEY COMMENT '주문 상세 ID',
  order_id INT NOT NULL COMMENT '주문 ID',
  menu_id INT NOT NULL COMMENT '상품 ID',
  menu_name VARCHAR(100) COMMENT '상품 이름(백업용)',
  quantity INT NOT NULL COMMENT '수량',
  unit_price INT NOT NULL COMMENT '개별 가격',
  FOREIGN KEY (order_id) REFERENCES orders(id),
  FOREIGN KEY (menu_id) REFERENCES menus(id)
) COMMENT='주문 상세 항목';
```

```db
6. 쿠폰 테이블
CREATE TABLE coupons (
  id INT AUTO_INCREMENT PRIMARY KEY COMMENT '쿠폰 ID',
  user_id INT NOT NULL COMMENT '유저 ID',
  name VARCHAR(100) COMMENT '쿠폰 이름',
  discount_rate FLOAT COMMENT '할인 비율 (예: 0.1 = 10%)',
  is_used BOOLEAN DEFAULT FALSE COMMENT '사용 여부',
  valid_until DATE COMMENT '유효기간',
  FOREIGN KEY (user_id) REFERENCES users(id)
) COMMENT='쿠폰 정보';
```

```db
7. 포인트 내역 테이블
CREATE TABLE point_histories (
  id INT AUTO_INCREMENT PRIMARY KEY COMMENT '포인트 내역 ID',
  user_id INT NOT NULL COMMENT '유저 ID',
  amount INT NOT NULL COMMENT '변동 포인트 (+적립 / -사용)',
  reason VARCHAR(255) COMMENT '포인트 증감 사유 (예: 주문 적립)',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP COMMENT '발생 일시',
  FOREIGN KEY (user_id) REFERENCES users(id)
) COMMENT='포인트 히스토리';
```

