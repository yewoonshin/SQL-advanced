# SQL_ADVANCED 4주차 정규 과제 

📌SQL_ADVANCED 정규과제는 매주 정해진 분량의 『*혼자 공부하는 SQL*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **SQL_ADVANCED_4th_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=DMNpkj_bZIs&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=13
https://www.youtube.com/watch?v=BUHj-behLyc&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=14
https://www.youtube.com/watch?v=JrXWxku7ZIM&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=15
-->

**교재 실습 예제 파일은 07_SQL_ADVANCED_Template 레포지토리의 src 폴더에 업로드되어 있습니다. market_db 파일도 해당 폴더에 함께 포함되어 있으니 참고하시기 바랍니다.**

**👀(수행 인증샷은 필수입니다.)** 

## SQL_ADVANCED_4th_TIL

### 5장 테이블과 뷰
#### 01. 테이블 만들기
#### 02. 제약조건으로 테이블을 견고하게
#### 03. SQL 가상의 테이블: 뷰 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~99    | ✅         |
| 2주차 | p.102~155   | ✅         |
| 3주차 | p.158~213  | ✅         |
| 4주차 | p.216~271 | ✅         |
| 5주차 | p.274~327 | 🍽️         |
| 6주차 | p.330~369 | 🍽️         |
| 7주차 | p.372~407 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 테이블 만들기 

<!-- 이번 챕터에서 제시된 실습을 흐름에 맞게 진행한 후, 실습 과정이 보일 수 있도록 인증 사진을 2장 이상 제출해 주세요. -->

<img width="453" height="342" alt="image" src="https://github.com/user-attachments/assets/6045c909-9a6f-48ae-b89d-96641636fa43" />
<img width="618" height="436" alt="image" src="https://github.com/user-attachments/assets/41bd92a0-aeb9-4dde-aea0-d2fad84193f2" />



## 2. 제약조건으로 테이블을 견고하게 

<!-- 제약조건에 관해 배우게 된 점을 적어주세요. -->
테이블을 만들때는 테이블 구조에 필요한 제약조건 설정 필요 
기본키, 외래키가 대표적인 제약 조건. 
-고유키: 이메일, 휴대폰과 같이 중복되지 않는 열에는 고유 키 지정 가능 , 기본키 제약 조건과 다른점은 null을 허용한다는 것 
-체크: 특정 값 이상 x 제약조건에 입력되는 데이터를 점검하는 기능. 
-기본값: 대한민국으로만 국적 설정처럼 값을 입력하지 않았을 떄 자동으로 입력될 값 지정 defualt 
-not null: 반드시 입력 

기본 키 제약 조건: 중복 불가, null값 입력 불가
제약조건 설정 방법 
- create table에서 마지막행헤 primary key 추가하기
- alter table구문 하용 (member 변경- 제약조건 추가 - mem_id 열에 기본키 제약조건 설정)
 # 외래키 
 외래키의 형식은 foreign key (열_이름) references 기준_테이블(열_이름) 
  - 설정 방법 (다른거) alter table구문 이용 
  - buy 수정 -> 제약 조건 추가 -> 외래 키 제약 조건을 buy 테이블의 mem_id에 설정 -> 참조 기준 테이블은 member 테이블의 mem_id
    ## 기준 테이블이 변경될 경우
    기본키- 외래키로 맺어진 후에는 기준 테이블의 열 이름이 변경되지 x
    on update cascade문은 기존 테이블의 데이터가 삭제되면 참조 테이블의 데이터도 삭제됨 

> **확인문제: 다음 보기 중에서 각 문항이 설명하는 것을 고르세요.**

보기는 아래와 같습니다.
```
CHECK / DEFAULT / PRIMAY KEY / UNIQUE / NOT NULL / FOREIGN KEY
```
🐷
```
여기에 답과 그 이유를 적어주세요!
1. 입력되는 데이터가 조건에 맞는지 검사하는 기능:check
2. 값을 입력하지 않으면 자동으로 들어갈 값:defualt
3. 빈 값을 입력하는 것을 허용하지 않음: not null 
```


## 3. 가상의 테이블: 뷰 

<!-- 뷰에 관해 배우게 된 점을 적어주세요. -->
뷰 = 데이터베이스 개체 중 하나 
단순 뷰 - 하나의 테이블과 연관된 뷰
복합 뷰- 2개 이상의 테이블과 연관된 뷰 
### 뷰의 기본 생성 
create view 뷰_이름
as
select 문; 
### 뷰의 작동 
뷰는 읽기 전용이지만 뷰를 통해 원본 테이블의 데이터를 수종 가능함 
### 뷰 사용 이유 
1. 보안에 도움이 됨 : 특정 칼럼만 보이는 뷰를 생성해 특정인에게 접근하지 못하도록 권한 제한
2. 복잡한 SQL 단순화 가능: 복잡한 쿼리를 자주 사용해야한다면 뷰로 생성해 놓고 사용자들은 해당 뷰에만 접근하도록 하면됨

### 뷰의 실제 작동
뷰의 실제 생성, 수정, 삭제 


1️⃣생성: create view v_viewtest1 as ~~~~~ ( 백틱을 사용) 


2️⃣수정: alter view 구문 사용 


3️⃣삭제: drop view 


정보 확인 가능 
describe문으로 기본 뷰의 정보 확인 가능 
show create view로 뷰의 소스 코드 확인 가능 
뷰를 통한 데이터의 수정, 삭제 : update ~~ 로 가능 
뷰가 참조하는 테이블 삭제: 참조하는 테이블이 없기 때문에 error 뜸 
뷰가 조회되지 않으면 check table문으로 뷰의 상태 확인 가능 
> **확인문제: 다음은 뷰의 특징입니다. 거리가 먼 것을 하나 고르세요.**

보기는 아래와 같습니다.
```
1️⃣ 뷰에는 테이블의 모든 열을 포함시켜야 합니다.
2️⃣ 뷰는 복잡한 SQL을 단순하게 만드는 효과가 있습니다.
3️⃣ 뷰는 보안에 도움이 됩니다.
4️⃣ 일부 사용자가 테이블에는 접근하지 못하게 하고, 뷰에만 접근하도록 설정할 수 있습니다.
```

```
여기에 답과 그 이유를 적어주세요!
```
1 
원하는 열만 넣어서 조합으로 조회가능 

---

# 2️⃣ 실습과제

## 1. 데이터베이스 구축

아래 코드를 MySQL Workbench에 붙여넣은 후,  
**전체 드래그 → 실행 (Ctrl + Shift + Enter)** 하여 데이터베이스를 생성하세요.

```sql
CREATE DATABASE IF NOT EXISTS week4_db;
USE week4_db;
```

## 2. 실습문제

1. 다음 조건을 만족하는 `users` 테이블을 생성하시오.
```
- user_id는 INT이며 **기본키(Primary Key)**로 설정합니다.
- name은 VARCHAR(20)이며 NULL을 허용하지 않습니다.
- email은 VARCHAR(50)이며 중복을 허용하지 않습니다.
- signup_date는 DATE 타입으로 설정합니다.
- grade는 INT이며 기본값(Default)을 1로 설정합니다.
```

2. 다음 조건을 만족하는 orders 테이블을 생성하시오.
```
- order_id는 INT이며 기본키(Primary Key)로 설정합니다.
- user_id는 INT이며 NULL을 허용하지 않습니다.
- amount는 INT이며 0보다 커야 합니다.
- order_date는 DATE 타입으로 설정합니다.
```

3. 다음 조건을 만족하여 데이터를 삽입하시오.
```
- users 테이블에 3명 이상의 데이터를 직접 INSERT 하시오.
- orders 테이블에 3건 이상의 데이터를 직접 INSERT 하시오.
```

4. users와 orders 테이블을 활용하여 다음 컬럼을 보여주는 뷰 user_order_view를 생성하시오.
```
- user_id
- name
- amount
```

5. 생성한 user_order_view를 조회하시오.

## 3. 제출 방법

1. 각 문제의 실행 결과가 보이도록 화면을 캡처합니다.
2. 테이블 생성 결과, 데이터 삽입 결과, 뷰 생성 및 조회 결과가 모두 보이도록 제출합니다.

<img width="813" height="52" alt="image" src="https://github.com/user-attachments/assets/1aa558b8-e37e-4e4b-b783-1f27b9fe9a45" />
<img width="868" height="776" alt="image" src="https://github.com/user-attachments/assets/bff23195-58ef-4137-8f53-fb046cad4778" />
<img width="585" height="395" alt="image" src="https://github.com/user-attachments/assets/2c038da6-c275-4e56-80c7-61b7c106b165" />

<img width="478" height="376" alt="image" src="https://github.com/user-attachments/assets/a4a815ac-30d8-40fe-8c40-944978d71939" />


### 🎉 수고하셨습니다.






