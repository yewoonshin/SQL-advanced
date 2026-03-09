# SQL-advanced
sql advanced 
# SQL_ADVANCED 1주차 정규 과제 

📌SQL_ADVANCED 정규과제는 매주 정해진 분량의 『*혼자 공부하는 SQL*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **SQL_ADVANCED_1st_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 제시된 강의를 참고하여 보완하는 것이 좋습니다.

<!-- 강의 링크는 아래와 같습니다.
https://www.youtube.com/watch?v=0cRhit1EJM0&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=1
https://www.youtube.com/watch?v=6JFEJWLcKUc&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=2
https://www.youtube.com/watch?v=8r1W_7nuo2U&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=3
https://www.youtube.com/watch?v=j2DAiY-OXGs&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=4
https://www.youtube.com/watch?v=EftIRlr6rPI&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=5
https://www.youtube.com/watch?v=lBk5YhLZevs&list=PLVsNizTWUw7GCfy5RH27cQL5MeKYnl8Pm&index=6
-->

**교재 실습 예제 파일은 07_SQL_ADVANCED_Template 레포지토리의 src 폴더에 업로드되어 있습니다. market_db 파일도 해당 폴더에 함께 포함되어 있으니 참고하시기 바랍니다.**

**👀(수행 인증샷은 필수입니다.)** 

## SQL_ADVANCED_1st_TIL

### 1장 데이터베이스와 SQL
#### 01. 데이터베이스 알아보기
#### 02. MySQL 설치하기
### 2장 실전용 SQL 미리 맛보기
#### 01. 건물을 짓기 위한 설계도: 데이터베이스 모델링
#### 02. 데이터베이스 시작부터 끝까지
#### 03. 데이터베이스 개체 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.24~99    | ✅         |
| 2주차 | p.102~155   | 🍽️         |
| 3주차 | p.158~213  | 🍽️         |
| 4주차 | p.216~271 | 🍽️         |
| 5주차 | p.274~327 | 🍽️         |
| 6주차 | p.330~369 | 🍽️         |
| 7주차 | p.372~407 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 데이터베이스 알아보기

<!-- 데이터베이스와 DBMS에 관해 배우게 된 점을 적어주세요. -->
데이터베이스에는 우리 생활 대부분의 정보가 저장되고 관리됨 
[DBMS의 정의] 
- 데이터베이스를 데이터의 집합이라고 정의한다면 데이터 베이스를 운영하는 소프트웨어를 DBMS라고 일컫는다.
[DBMS의 종류]
대표적으로 MYSQL, oracle, sql server, madiadb가 있다.
- DBMS에 데이터를 구축, 관리하고 활용하기 위해 사용되는 언어가 SQL이다.
  
[DBMS의 분류]
1) 계층형
   - 처음 등장한 개념. 각 계층은 트리 형태를 갖는다
   - 구성 완료 후 변경이 까다롭다(지금은 사용X)
2) 망형 DBMS
   - 계층형의 문제를 개선하기 위해 등장
   - 하위에 있는 구성원들끼리도 연결된 구조
3) 관계형 DBMS
   - 테이블이라는 최소단위로 구성됨, 이 테이블은 하나 이상의 열과 행으로 이루어짐
   - 모든 데이터가 테이블에 저장되고 이 구조가 가장 기본적이고 중요한 구성
  [SQL]
- DBMS에서 사용되는 언어
[핵심 정리]
1. 데이터베이스는 데이터 집합, DBMS 는 데이터베이스를 운영/관리하는 프로그램을 말함
2. 테이블은 데이터베이스의 최소단위로 하나 이상의 열과 행으로 구성되어 있다
3. SQL 은 데이터베이스 구축, 관리하고 활용하기 위해 사용되는 언어 
   

> **확인문제: 다음 소프트웨어 중에서 DBMS가 아닌 것을 모두 고르세요.**

> MySQL / Excel / Oracle / SQL Server / MariaDB

```
여기에 답을 적어주세요!
```
엑셀 

## 2. MySQL 설치하기

<!-- 이번 챕터는 개념정리 없이 MySQL 설치 후 인증사진으로 대체합니다. -->
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/795a84fb-2f6d-4c9a-8be5-72ec15354bca" />



## 3. 건물을 짓기 위한 설계도: 데이터베이스 모델링

<!-- 데이터베이스 모델링에 관해 배우게 된 점을 적어주세요. -->

> **확인문제: 다음은 폭포수 모델의 절차입니다. 차례대로 나열해보세요.**

> 시스템 설계 / 테스트 / 프로그램 구현 / 프로젝트 계획 / 업무 분석 / 유지보수

```
여기에 답을 적어주세요!
```
- 데이터베이스 모델링은 테이블의 구조를 미리 설계하는 개념
- 프로젝트를 진행하기위해서는 대표적으로 폭포수 델 사용
[프로젝트]
- 현실세계에서 일어나는 업무를 컴퓨터 시스템으로 옮기는 과정
- 대규모 소프트웨어를 작성하기 위한 전체 과정
[폭포수 모델]
1. 프로젝트 계획
2. 업무분석
3. 시스템 설계
4. 프로그램 구현
5. 테스트
6. 유지보수
[데이터베이스 모델링]
- 실제 상황(작업)을 DBMS의 데이터베이스 개체로 옮기기 위한 과정
[데이터베이스 구성도]
- 데이터: 하나의 단편적인 정보
- 테이블: 회원, 제품의 데이터를 입력하기 위해 표 형태로 표현한 것
- 데이터베이스: 테이블이 저장되는 저장소를 말합니다. 
- DBMS: 데이터베이스 관리 시스템 또는 소프트웨어
- 열:테이블의 세로
- 열 이름: 각 열을 구분하기 위한 이름
- 데이터 형식: 열에 저장된 데이터의 형식. 숫자, 문자, 정수 등등
- 행: 실질적인 진짜 데이터. 행 데이터라고도 부르며 행의 개수가 즉 데이터의 개수
- 기본키: 열은 각 행을 구분하는 유일한 열을 일컬음. 테이블에는 열이 여러개 있지만 기본키는 1개만 지정, 일반적으로 1개의 열에 지정 
## 4. 데이터베이스 시작부터 끝까지 

<!-- 이번 챕터는 개념정리 없이 실습 인증사진으로 대체합니다. 강의를 수강하고, 실습 과정이 보이도록 인증사진 3-4장을 아래에 제출해주세요. -->

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/5acd8b71-21c6-421e-87d9-b7bfb22ac034" />

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/5e679423-a8ae-438d-a1bd-7ec3cb755f14" />

<img width="1395" height="1008" alt="image" src="https://github.com/user-attachments/assets/e149d3b8-3f68-47ec-8c15-bd864c3c6f2e" />

<img width="1395" height="1008" alt="image" src="https://github.com/user-attachments/assets/9763e9e0-53e2-48c4-ac34-47c64d76a224" />

<img width="1401" height="1021" alt="image" src="https://github.com/user-attachments/assets/c3671525-fc97-4f9e-9a28-80f5f2a9ed4c" />


## 5. 데이터베이스 개체

<!-- 데이터베이스 개체에 관해 배우게 된 점을 적어주세요. -->

<!-- 인덱스, 뷰, 스토어드 프로시저 실습을 각각 진행한 후, 각 실습에 대한 인증 사진을 1장씩 제출해 주세요. -->

<img width="1402" height="1002" alt="image" src="https://github.com/user-attachments/assets/55987fa8-ad49-4464-9b83-d0675714f1f6" />

<img width="1402" height="1002" alt="image" src="https://github.com/user-attachments/assets/967a491c-d7ce-4a1c-80d9-4ef0eb5d6288" />
<img width="1360" height="1007" alt="image" src="https://github.com/user-attachments/assets/889e58eb-3ad7-4a0f-bd8a-7db710a9e88e" />

---

# 2️⃣ 실습과제

> SQL ADVANCED 과정은 별도의 확인문제가 없습니다. 다음 주부터는 확인문제 대신 제공되는 실습용 테이블을 활용하여, 배운 내용을 직접 적용하는 실습형 과제로 진행됩니다.

> 이번주는 개강과 함께 새로운 학기가 시작된 만큼, 학기 초 일정에 천천히 적응하시며 부담 없는 한 주 보내시길 바랍니다. 😊

### 🎉 수고하셨습니다.






