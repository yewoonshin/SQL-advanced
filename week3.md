# SQL_ADVANCED 3주차 정규 과제 

📌SQL_ADVANCED 정규과제는 매주 정해진 분량의 『*혼자 공부하는 SQL*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **SQL_ADVANCED_3rd_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=1YmWy-7-OhQ&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=10
https://www.youtube.com/watch?v=tuQFkzjqEGw&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=11
https://www.youtube.com/watch?v=IOCsreDYqFE&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=12
-->

**교재 실습 예제 파일은 07_SQL_ADVANCED_Template 레포지토리의 src 폴더에 업로드되어 있습니다. market_db 파일도 해당 폴더에 함께 포함되어 있으니 참고하시기 바랍니다.**

**👀(수행 인증샷은 필수입니다.)** 

## SQL_ADVANCED_3rd_TIL

### 4장 SQL 고급 문법
#### 01. MySQL의 데이터 형식
#### 02. 두 테이블을 묶는 조인
#### 03. SQL 프로그래밍 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~99    | ✅         |
| 2주차 | p.102~155   | ✅         |
| 3주차 | p.158~213  | ✅         |
| 4주차 | p.216~271 | 🍽️         |
| 5주차 | p.274~327 | 🍽️         |
| 6주차 | p.330~369 | 🍽️         |
| 7주차 | p.372~407 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. MySQL의 데이터 형식
<!-- MySQL의 데이터 형식에 관해 배우게 된 점을 적어주세요. -->
1. 정수형
- 소수점이 없는 숫자
- 주로 인원수, 가격, 수량등에 사용
- 1) TINYINT : 바이트수 1
  2) SMALLINT: 바이트수 2
  3) INT:바이트수 4
  4) BIGINT:바이트수 8
2. 문자형
   -글자를 저장하기 위해 사용, 입력할 최대 글자 개수 지정
   - 대표적인 문자형은 char(최대255), varchar(최대 16383) 
   - char은 글자 개수 고정된 경우, varchar은 글자 개수가 변동될 경우 사용하는것이 좋음
   - 예를 들어 거주지역을 서울/부산/경기/전남 과같이 시도만 저장할 경우 모두 두글자 CHAR(2)
   - 반면 음식이름 마라탕, 마라샹궈 등 VARCHAR
   - 또한 연락처 저장할때 제일앞에 0이붙어야하는데 정수형으로 지정하면 0이 사라져 문자열로 지정
   - 숫자가 숫자로서의 의미를 가질 조건
     1) 더하기/빼기 등의 연산에 의미가 있다
     2)  크다/ 작다 또는 순서에 의미가 있다
2-2. 대량의 데이터 형식
- 더 큰 데이터 형식을 저장하기 위해서 text(최대 65535), longtext(최대 42억자) : 주로 대본
- BLOB: 동영상등의 데이터

3. 실수형
   - 실수형은 소수점이 있는 숫자를 저장할때 사용
   - float(소수점 아래 7자리까지)  double(소수점 아래 15자리까지) 은 거의 비슷 
   - 과학 기술용 데이터가 아닌 이상 float이 나음
4. 날짜형
   - 날짜 및 시간 저장할 때 사용
   -1) DATE : YYYY-MM-DD
   -2) TIME: HH:MM:SS
   -3) DATETIME: YYYY-MM-DD HH:MM:SS형식
5. 변수사용
   변수 선언과 값 대입은
   SET @변수이름 =변수의 값;
   SELECT @변수이름;
6. 데이터 형 변환
   문자형 -> 정수형 or 정수형 -> 문자형 
   A. 명시적변환: 직접 함수를 사용해 변환
   - cast, convert
   B. 암시적변환: 별도의 지시 없이 자연스럽게 변환됨 



> **확인문제: 다음 보기에서 데이터 형식의 변환에 사용되는 함수를 2개 고르세요.**

보기는 아래와 같습니다.
```
CONVERT() / DATA() / CAST() / MOVE() / TYPE() / SUM() / AVG() / CURRENT_DATE()
```

```
cast, convert
```


## 2. 두 테이블을 묶는 조인

<!-- 두 테이블을 묶는 조인에 관해 배우게 된 점을 적어주세요. -->
조인= 두개의 테이블을 묶어 하나의 결과를 만들어내는것 
[내부조인] 
-일대다 관계: 한쪽 테이블에는 하나의 값만 존재해야하지만 연결된 다른 테이블에는 여러개의 값이 존재할 수 있는 관계 
 ex. 회원 테이블에서 블랙핑크 아이디는 BLK로 1명밖에 없음, 따라서 회원 테이블 아이디를 기본 키로 설정. 구매 테이블의 아이디에서는 3개의 BLK 찾을 수 있음. 즉 회원은 한명이지만 회원은 여러번 구매 가능 . 따라서 구매 테이블의 아이디는 외래키로 설정 
 이러한 관계를 일대다 관계라고 함
 내부 조인 형식 
 select <열 목록>
 from <첫번쨰 테이블>
 inner join <두번째 테이블>
 on <조인될 조건>
 where 검색 조건 컬럼

 [내부조인] 
 두 테이블을 조인할 때 필요한 내용이 한쪽 테이블에만 있어도 결과를 추출 가능 
 select <열 목록> 
 from <첫번째 테이블(=left 테이블)>
 <left/right/full> outer join <두번째테이블(right 테이블)>
 on <조인될 조건>
 [where 검색 조건]; 

 1) left outer join: 왼쪽 테이블의 내용은 모두 출력되어야 한다
 2) right outer join: 오른쪽 테이블의 내용은 모두 출력되어야 한다
 3) full outer join: 왼쪽 외부 조인과 오른쪽 외부 조인이 합쳐짐
 4) cross join: 한쪽 테이블의 모든행과 다른쪽 테이블의 모든 행 조인
 5) 자체 조인: 자신의 자신과 조인한다는 의미 

> **확인문제: 다음 SQL은 회원으로 가입만 하고, 한 번도 구매한 적이 없는 회원의 목록을 조회하는 쿼리입니다. 빈칸에 들어갈 가장 적절한 구문을 고르세요..**

```sql
SELECT DISTINCT M.mem_id, B.prod_name, M.mem_name, M.addr
  FROM member M
    LEFT OUTER JOIN buy B
    ON M.mem_id = B.mem_id
  __________
  ORDER BY M.mem_id;
```
보기는 아래와 같습니다.
```
1. JOIN B.prod_name IS NULL
2. LIMIT B.prod_name IS NULL
3. HAVING B.prod_name IS NULL
4. WHERE B.prod_name IS NULL
```
```
4. 
```

## 3. SQL 프로그래밍 

<!-- IF문, CASE문, WHILE문, 동적 SQL에 관해 배우게 된 점을 적어주세요. -->
if 문: 참이라면 실행, 그렇지 않으면 넘어감 
if else: 조건에 따라 다른 부분 수행
case: case와 end case 사이에는 여러 조건을 넣을 수 있음. when 조건이 여러개라면 when을 여러개 반복 
예를 들어 90점 이상 A, 80점 이상 B 이런식 
최우수 고객 , 우수 고객, 일반고객, 유령 고객 이런식으로 범주화 가능 
while: 조건이 만족되는 동안에는 계속 같은 내용 반복 가능 
동적 SQL 
prepare- SQL을 실행하지 않고 미리 준비만 해놓음
execute- 준비한 SQL문 실행 
> **확인문제: 다음은 CASE 문의 형식입니다. 빈칸에 들어갈 가장 적절한 명령어를 보기에서 고르세요..**

```sql
CASE
    (1) 조건 THEN
        SQL문장들1
    ELSE
        SQL문장들4
END (2);
```

보기는 아래와 같습니다.
```
WHEN / THEN / CURRENT / DATE / TIME / IF / END IF / CASE
```

```
여기에 답을 적어주세요!
(1) when 
(2) case
```


---

# 2️⃣ 실습과제

## 1. 데이터베이스 구축

아래 코드를 MySQL Workbench에 붙여넣은 후,  
**전체 드래그 → 실행 (Ctrl + shift + Enter)** 하여 데이터베이스를 구축하세요.

```sql
-- 1. 데이터베이스 생성
CREATE DATABASE IF NOT EXISTS week3_db;

-- 2. 사용할 데이터베이스 선택
USE week3_db;

-- 3. 기존 테이블 삭제 (초기화용)
DROP TABLE IF EXISTS orders;
DROP TABLE IF EXISTS customers;

-- 4. 테이블 생성 (조인 실습용)
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    name VARCHAR(20),
    signup_date_str VARCHAR(8) 
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,           
    order_date_str VARCHAR(8), 
    amount_str VARCHAR(10)     
);

-- 5. 데이터 삽입
INSERT INTO customers VALUES
(1, '진아', '20240218'),
(2, '혜인', '20230302'),
(3, '규서', '20220315'),
(4, '규영', '20210401'),
(5, '철원', '20230909'),
(6, '예운', '20240201'),
(7, '민서', '20220320'),
(8, '광윤', '20240105'); -- 주문 없는 고객(외부 조인용)

INSERT INTO orders VALUES
(101, 1, '20240220', '12000'),
(102, 1, '20240303', '30000'),
(103, 2, '20240111', '15000'),
(104, 3, '20221201', '9000'),
(105, 5, '20231111', '20000'),
(106, 7, '20220707', '5000'),
(107, 99, '20240210', '7000'); -- 고객 테이블에 없는 customer_id (외부 조인용)
```

## 2. 실습 문제

다음 SQL 문을 작성하고 실행 결과를 확인 후 인증 사진을 아래에 업로드하세요.

1. **데이터 형식 변환**
   - orders 테이블의 `order_date_str`을 DATE 형식으로 변환하여 조회하시오.
   (힌트: STR_TO_DATE 사용)

<img width="201" height="197" alt="image" src="https://github.com/user-attachments/assets/049cad57-e97a-4b97-ae15-bf824d3e12eb" />


2. **데이터 형식 변환**
   - orders 테이블의 `amount_str`을 숫자형으로 변환하여 조회하시오.
   - <img width="232" height="218" alt="image" src="https://github.com/user-attachments/assets/b703be3e-657b-4a49-a919-675af263167b" />


3. **내부 조인 (INNER JOIN)**
   - customers와 orders를 customer_id 기준으로 내부 조인하여
     고객 이름(name)과 주문 번호(order_id)를 함께 조회하시오
     <img width="168" height="156" alt="image" src="https://github.com/user-attachments/assets/0909c5fd-4d11-4bbe-aed3-23f655835af9" />


4. **외부 조인 (LEFT JOIN)**
   - customers를 기준으로 LEFT JOIN을 수행하여,
     주문이 없는 고객도 함께 조회하시오.
     <img width="175" height="247" alt="image" src="https://github.com/user-attachments/assets/3f386313-5c99-4c6a-8d12-704f57d63057" />


5. **스토어드 프로시저 (IF문 사용)**
   - 입력받은 금액이 10000 이상이면 '고액 주문',
     그렇지 않으면 '일반 주문'을 출력하는
     프로시저를 생성하시오.
   - 생성 후 CALL로 실행 결과를 확인하시오.


<img width="476" height="447" alt="image" src="https://github.com/user-attachments/assets/bad240ae-e7d6-44af-afee-a02c71c3ec56" />



### 🎉 수고하셨습니다.






