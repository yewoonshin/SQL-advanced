# SQL_ADVANCED 6주차 정규 과제 

📌SQL_ADVANCED 정규과제는 매주 정해진 분량의 『*혼자 공부하는 SQL*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **SQL_ADVANCED_6th_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=cw1wGN0ZdFA&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=19
https://www.youtube.com/watch?v=bMQ_dAoaMzA&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=20
https://www.youtube.com/watch?v=bggWVsBmKag&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=21
-->

**교재 실습 예제 파일은 07_SQL_ADVANCED_Template 레포지토리의 src 폴더에 업로드되어 있습니다. market_db 파일도 해당 폴더에 함께 포함되어 있으니 참고하시기 바랍니다.**

**👀(수행 인증샷은 필수입니다.)** 

## SQL_ADVANCED_6th_TIL

### 7장 스토어드 프로시저
#### 01. 스토어드 프로시저 사용 방법
#### 02. 스토어드 함수와 커서
#### 03. 자동 실행되는 트리거 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~99    | ✅         |
| 2주차 | p.102~155   | ✅         |
| 3주차 | p.158~213  | ✅         |
| 4주차 | p.216~271 | ✅         |
| 5주차 | p.274~327 | ✅         |
| 6주차 | p.330~369 | ✅         |
| 7주차 | p.372~407 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 스토어드 프로시저 사용 방법 

<!-- 스토어드 프로시저에 관해 배우게 된 점을 적어주세요. -->
### 개념과 형식 
스토어드 프로시저란 MYSQL에서 제공하는 프로그래밍 기능 
스토어드 프로시저는 쿼리 문의 집합으로도 볼 수 있으며 어떠한 동작을 일괄 처리하기 위한 용도로도 사용 
자주 사용하는 일반적 쿼리를 반복하는 것보다 스토어드 프로시저로 묶어놓고 필요할 때마다 간단히 호출만 하면 훨씬 편리하게 MYSQL 운영 가능 

### 매개변수 사용 
스토어드 프로시저에서 실행 시 입력 매개변수 지정 가능 
입력 매개변수의 경우 지정 형식은 IN 입력_매개변수_이름 데이터_형식과 같음 
출력 매개변수의 경우 스토어드 프로시저에서 계산된 결과를 돌려받으며 형식은 out을 앞에 붙임 
### SQL 프로그래밍의 활용 
동적 SQL은 다이나믹하게 SQL을 생성한 후 실행되며 prepare문과 execure문을 사용함 

<!-- 이번 챕터에서는 확인문제를 실습 인증으로 대체하여 진행합니다. 제시된 실습을 흐름에 맞게 진행한 후, 실습 과정이 보일 수 있도록 인증 사진을 2장 이상 제출해 주세요. -->

<img width="646" height="445" alt="image" src="https://github.com/user-attachments/assets/f84062de-4829-4fff-9c54-ef96c16351da" />
<img width="642" height="292" alt="image" src="https://github.com/user-attachments/assets/6c5e99dd-85a5-461b-b620-be3a658d9789" />




## 2. 스토어드 함수와 커서 

<!-- 스토어드 함수와 커서에 관해 배우게 된 점을 적어주세요. -->
스토어드 함수는 MySQL에서 제공하는 내장 함수 외에 직접 함수를 만드는 기능을 제공함. 즉 MYSQL이 제공하는 함수를 그대로 사용할 수 없는 경우가 
발생한다면 직접 스토어드 함수 작성 가능 
커서는 스토어드 프로시저 안에서 한 행씩 처리할 때 사용한느 프로그래밍 방식 
### 스토어드 함수의 개념과 형식
사용자가 직접 함수를 만들어서 사용 가능하고 이러한 함수를 스토어드 함수라고 부름 
- 스토어드 함수는 returns 문으로 반환할 값의 데이터 형식을 지정하고 본문 안에서는 return문으로 하나의 값을 반환해야함
-  스토어드 함수의 매개변수는 모두 입력 매개변수이며 in을 붙이지 않음
- 스토어드 프로시저는 call로 호출하지만 스토어드 함수는 select 문 안에서 호출됨

### 커서의 기본 개념 
커서는 테이블에서 한 행씩 처리하기 위한 방식

### 스토어드 함수의 사용 
스토어드 함수 사용을 위해선 먼저 SQL로 스토어드 함수 생성 권한을 허용해줘야함 
SET GLOBAL log_bin_trust_function_creators=1; 
커서는 행이 끝날때까지 계속 반복하며 행의 끝을 판단하기 위해 변수 endOfRow를 준비하고 true값인지 체크하는 방식을 사용함 


<!-- 이번 챕터에서는 확인문제를 실습 인증으로 대체하여 진행합니다. 제시된 실습을 흐름에 맞게 진행한 후, 실습 과정이 보일 수 있도록 인증 사진을 2장 이상 제출해 주세요. -->
<img width="597" height="377" alt="image" src="https://github.com/user-attachments/assets/e05d1810-3dba-41f3-bb00-ed3c9ff1f542" />




## 3. 자동 실행되는 트리거 

<!-- 트리거에 관해 배우게 된 점을 적어주세요. -->
트리거는 자동으로 수행하여 사용자가 추가 작업을 잊어버리는 실수를 방지함 
트리거를 사용하면 데이터에 오류가 발생하는 것을 막을 수 있으며 데이터의 무결성이라고 부름 
### 개요 
트리거는 테이블에서 DAML 문의 이벤트가 발생할 때 작동함 
트리거는 행 데이터가 삭제 또는 수정되면 기존 데이터를 백업 테이블에 저장하도록 할 수 있음 
### 활용 
트리거는 테이블에 입력, 수정, 삭제되는 정보를 백업하는 용도로 활용 가능 
### 임시 테이블 
DML 작업이 수행되면 임시로 사용되는 시스템 테이블 2개가 있는데 new와 old
두 테이블은 사용자가 만드는 것 x MYSQL이 알아서 생성하고 관리함 


<!-- 이번 챕터에서는 확인문제를 실습 인증으로 대체하여 진행합니다. 제시된 실습을 흐름에 맞게 진행한 후, 실습 과정이 보일 수 있도록 인증 사진을 2장 이상 제출해 주세요. -->

<img width="627" height="236" alt="image" src="https://github.com/user-attachments/assets/8ea9593e-0da1-4654-84ac-a53793e4094a" />



---

# 2️⃣ 실습과제

## 1. 데이터베이스 구축

아래 코드를 MySQL Workbench에 붙여넣은 후,  
**전체 드래그 → 실행 (Ctrl + Shift + Enter)** 하여 데이터베이스를 구축하세요.

```sql
CREATE DATABASE IF NOT EXISTS week6_db;
USE week6_db;

-- 초기화
DROP TABLE IF EXISTS transactions;
DROP TABLE IF EXISTS accounts;

-- 계좌 테이블
CREATE TABLE accounts (
    acc_id INT PRIMARY KEY,
    name VARCHAR(20) NOT NULL,
    balance INT NOT NULL DEFAULT 0 CHECK (balance >= 0)
);

-- 거래 테이블
CREATE TABLE transactions (
    tx_id INT PRIMARY KEY,
    acc_id INT NOT NULL,
    amount INT NOT NULL,
    tx_date DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP
);

-- 샘플 데이터
INSERT INTO accounts VALUES
(1, '진아', 20000),
(2, '혜인', 8000),
(3, '규서', 55000),
(4, '규영', 12000);
```

## 2. 실습 문제

다음 문제를 수행하고 실행 결과를 확인 후 인증 사진을 아래에 업로드하세요.
(추가 수행도 필수입니다.)


### 1. 스토어드 프로시저

**다음 요구사항을 만족하는 프로시저 `sp_add_balance`를 생성하시오.**
- 입력값: `p_acc_id INT`, `p_amount INT`
- 기능:
  - 해당 계좌의 `balance`에 `p_amount`를 더합니다.

**추가 수행**
- 프로시저를 1회 이상 CALL 하시오.
- 실행 후 `accounts` 테이블을 조회하여 잔액이 변경되었는지 확인하시오.

---
<img width="245" height="127" alt="image" src="https://github.com/user-attachments/assets/cd632aa4-1b3d-45d7-a854-d9b45e626cd0" />


### 2. 스토어드 함수

**다음 요구사항을 만족하는 함수 `fn_is_vip`를 생성하시오.**
- 입력값: `p_balance INT`
- 반환값:
  - `p_balance >= 50000` 이면 `'VIP'`
  - 그렇지 않으면 `'일반'`

**추가 수행**
- `accounts` 테이블을 조회하면서 `fn_is_vip(balance)` 결과를 함께 출력하시오.

---
<img width="332" height="126" alt="image" src="https://github.com/user-attachments/assets/bd1be559-1f8a-4002-b492-1f78a50d7433" />


### 3. 커서(Cursor)

**accounts 테이블의 모든 계좌를 커서로 순회하면서 각 계좌의 `name`과 `balance`를 출력하는 프로시저를 작성하시오.**

**추가 수행**
- 프로시저를 CALL 하여 결과를 확인하시오.
- <img width="336" height="60" alt="image" src="https://github.com/user-attachments/assets/091eec0a-36f6-44dd-abac-7438e3a3ee70" />


---

### 4. 트리거(Trigger)

**transactions 테이블에 새로운 데이터가 INSERT 될 때 해당 `acc_id`의 `accounts.balance`가 자동으로 증가하도록 트리거를 생성하시오.**

**추가 수행**
- transactions에 직접 INSERT 하시오.
- accounts 잔액이 자동으로 증가하는지 확인하시오.


<img width="686" height="298" alt="image" src="https://github.com/user-attachments/assets/3f622f62-6e7a-40db-93cd-fb430d93834b" />



### 🎉 수고하셨습니다.






