# SQL_BASIC 5주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_5th_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**5주차 과제는 문제 풀이를 중심으로**, 강의에서 제시된 예제 문제 중 **3 문제 이상을 선택하여 직접 풀어본 뒤**, 강의 영상의 풀이와 비교해 **틀린 부분, 맞은 부분, 새롭게 배운 개념**을 구체적으로 정리해주세요. (적어도 4문제는 정리해야 합니다.) 완성된 과제는 Gihub에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**(수행 인증샷은 필수입니다.)** 



## SQL_BASIC_5th

### 섹션 5. 데이터 탐색 - 변환

### 4-4. 날짜 및 시간 데이터 이해하기(2) (EXTRACT, DATETIME_TRUNC, PARSE_DATETIME, FROMAT_DATETIME)

### 4-5. 시간 데이터 연습문제 1~2번

### 4-5. 시간 데이터 연습문제 3~5번

### 4-6. 조건문 (CASE WHEN, IF)

### 4-7. 조건문 연습 문제

### 4-8. 정리

### 4-9. BigQuery 공식 문서 확인하는 법

(강의에서 연습문제가 많아서 따로 프로그래머스 문제 과제는 없습니다.)



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | ✅         |
| 4주차 | 섹션 **3-4** ~ **4-4** | ✅         |
| 5주차 | 섹션 **4-4** ~ **4-9** | ✅         |
| 6주차 | 섹션 **5-1** ~ **5-7** | 🍽️         |
| 7주차 | 섹션 **6-1** ~ **6-6** | 🍽️         |

<br>



<!-- 여기까진 그대로 둬 주세요-->

---

# 4-4. 날짜 및 시간 데이터 이해하기(2) (EXTRACT, DATETIME_TRUNC, PARSE_DATETIME, FROMAT_DATETIME)

~~~
✅ 학습 목표 :
* 날짜 및 시간 데이터에 대해서 더 자세히 설명할 수 있다. 
* CURRENT_TIME, EXTRACT, DATETIME_TRUNC, PARSE_DATETIME, FROMAT_DATETIME 을 설명할 수 있다. 
~~~
1. DATETIME 함수

 2-1. CURRENT_TIME([time_zone)]
    - 현재 DATETIME 출력

  2-2. EXTRACT: DATETIME에서 특정 부분만 추출하고 싶은 경우
    - EX) 2024-01-02 14:00:00에서 연도, 월, 일 에서 원하는 데이터를 뽑아내는 것.
    - 일자별 주문, 월별 주문 확인하고 싶은 경우.
  
  2-3. DATETIMe_TRUNC: DATE와 HOUR만 남기고 싶은 경우 => 시간 자르기
    - DATETIME_TRUNC(datetime_col, HOUR)
    - "2024-01-02 14:42:13"을 HOUR로 자르면 -> "2024-01-02 14:00:00"
  
  2-4. PARSE_DATETIME
    - 문자열로 저장된 DATETIME을 DATETIME 타입으로 바구고 싶은 경우
    - PRASE_DATETIME('문자열의 형태', 'DATETIME 문자열') AS datetime
   <img width="879" height="258" alt="image" src="https://github.com/user-attachments/assets/bba86cc2-e994-4f77-bf37-d15422cedc92" />

  2-5. FORMAT_DATETIME
    - DATETIME 타입 데이터를 특정 형태의 문자열 데이터로 변환하고 싶은 경우
    <img width="822" height="81" alt="image" src="https://github.com/user-attachments/assets/0a51a96d-e978-410d-9e89-43b667b6e0bf" />


     
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



# 4-6. 조건문(CASE WHEN, IF)

~~~
✅ 학습 목표 :
* 조건문 함수의 기능을 이해하고, 설명할 수 있다. 
~~~

<조건문>
- 만약 특정 조건이 충족되면, 어떤 행동을 하자
- 특정 조건이 참일때 A, 아니면 B
  - 조건에 따른 분기 처리가 필요한 경우
- 조건에 따라 다른 값을 표시하고 싶을 때 사용

- 조건문을 사용하는 방법
   1) CASE WHEN
   2) IF
 - CASE WHEN: 여러 조건이 있을 경우 사용. 조건의 순서에 주의
 - IF: 단일 조건일 경우 사용
1. CASE WHEN
 - 여러 조건이 있을 경우 유용
~~~
- 문법
SELECT
 CASE
  WHEN 조건1 THEN 조건 1이 참일 경우 결과
  WHEN 조건2 THEN 조건2가 참일 경우 결과
  ELSE 그 외 조건일 경우 결과
END AS 새로운_컬럼_이름
FROM
~~~
- ROW 순서로 계산하기 때문에, 조건을 작성할때 순서에 대한 주의가 필요함. EX) 작은 수 -> 큰 수

 2. IF
~~~
- 문법
IF(조건문, True일 때의 값, Fasle일 때의 값) AS 새로운_칼럼_이름
~~~
<img width="1315" height="311" alt="image" src="https://github.com/user-attachments/assets/48688031-9f05-4110-bb62-2ed2c4d844b5" />

  - 
SELECT
 IF(1=1, '동일한 결과', '동일하지 않은 결과') AS result1,
 IF(1=2, '동일한 결과', '동일하지 않은 결과') AS result2
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



 # 4-5. 시간 데이터 연습문제 & 4-7. 조건문 연습 문제

~~~
✅ 학습 목표 :
* 4-5, 4-7 각각에서 두 문제 이상 (최소 4문제) 푼 내용 정리하기
~~~


**<시간 데이터 연습 문제>**

~~~
1번 문제: 데이터의 특징을 꼭 직접 파악하고 넘어가기

- catch_date : DATE  타입
- catch_datetime: UTC, TIMESTAMP 타입 => 컬럼의 이름은 datetime인데 TIMESTAMP으로 저장되어 있음
- 컬럼의 이름만 믿고 바로 쿼리를 시작하는 것이 아니라, 꼭 이렇게 데이터를 확인해야함
- catch_date => KR? UTC? 어떤 기준??
- catch_date 칼럼 catc_datetime 컬럼을 비교 => DATETIME(catch_datetime, "Asia/Seoul")
- catch_date != DATE(DATETIME(catch_datetime, "Asia/Seoul")) => 있다면 catch_date는 사용하기 어려움
~~~

~~~
2번 문제: 오답

- 먼저 battle_date는 battle_datetime을 기반으로 만들어진 DATE임을 확인
- 그러나 battle_datetime, battle_timestamp 를 검증 해야함 -> 서로 같음을 확인
- EXTRACT 와 HOUR를 사용하여 그 사이의 시간을 구해야함. HOUR을 사용 못함
~~~
~~~
3번 문제: 오답

- 포획한 첫날을 구하는 방법 = MIN()을 사용한다. DATE 데이터도 최솟값이 존재 (GROUP BY 필수)
- FORMAT_DATE를 통해 DATE 데이터를 문자열로 변경. dd/mm/yy형태로 바꾸는 명령어는 찾아서
- catch_date 칼럼은 UTC이기 때문에, catch_datetime 데이터를 사용하여 DATE() 함수를 통해 Asia/Seoul로 바꿔줘야함
- ORDER_BY는 연산 효율상 맨 마지막에 위치.
~~~
~~~
5번 문제: 오답

- 서브쿼리에서 칼럼 선택을 catch_datetime으로 함. -> trainer_id로 해야됨
- 큰 쿼리에서 칼럼 선택을 안해줌 -> *로 해줘야함.
- MAX - MIN으로 계산함. -> DATETIME_DIFF 라는 좋은 함수가 존재

의문! => 3번 문제에서 UTC를 바꿔줄 때, DATE() 함수를 썼는데 왜 이번에는 DATETIME() 인가??
~~~

**<조건문 연습 문제>**

~~~
2번 문제: 오답

- WEHN 절을 3개를 작성해야 하는데 WHEN 절을 하나로 묶고 3개의 조건을 OR로 연결하려 해서 오답.
~~~
~~~
3번 문제: 오답

- ELSE에 어떤 값을 넣어야 할지 몰랐음. 그냥 300이하를 WHEN절로 쓰지 않고 ELSE 절에 넣으면 해결됨
- 그러나 'LOW'는 ELSE절에 생긴 값이라 total_grade에서 보여지지 않기 때문에 서브쿼리로 묶고 난 뒤 WHERE절을 사용하여 값을 확인 할 수 있음
~~~
~~~
5번 문제: 오답

- catch_date 칼럼을 사용해서 IF (catch_date >= ~~~) 이런식으로 진행
- catch_datetime을 사용해야하고, 그럴 경우 UTC 이기 때문에, DATE( ~~` "Asia/Seoul")을 사용해야함.
~~~

<br>
<img width="403" height="871" alt="image" src="https://github.com/user-attachments/assets/b6013f3a-8812-4ecd-84dc-a955eab37577" />

<br>

---

# 확인문제

## 문제 1

> **🧚Q. 광윤이는 사용자 로그 데이터에서, 2021년에 접속한 사용자 수를  집계하려고 했습니다. 그는 여러 SQL 쿼리들을 실행해봤지만, 그 중 일부는 문법적으로 잘못되어 실행되지 않았습니다. 다음 보기 중 틀린 쿼리를 모두 골라보세요 (복수 선택 가능)**

~~~sql
1. SELECT COUNT(*)  
   FROM user_log  
   WHERE EXTRACT(YEAR FROM login_date) = 2021;

2. SELECT EXTRACT(YEAR FROM login_date), COUNT(*)  
   FROM user_log  
   GROUP BY EXTRACT(YEAR FROM login_date);

3. SELECT COUNT(*)  
   FROM user_log  
   WHERE login_date = '2021';

4. SELECT COUNT(*)  
   FROM user_log  
   WHERE login_date BETWEEN '2021-01-01' AND '2021-12-31';
~~~

<!-- 틀린쿼리에 대한 오류의 원인도 같이 작성해주세요. 문제에서 제공된 login_data 컬럼은 DATE type의 데이터를 가지고 있다고 가정하시면 됩니다. -->

~~~
여기에 답을 작성해주세요!
~~~



## 문제 2

> **🧚Q. 혜성이는 포켓몬 타입에 따라 설명을 부여하는 쿼리를 작성했습니다. type 1 컬럼의 값에 따라 조건을 분기했으며, 다음 SQL 쿼리를 실행했습니다.**

~~~sql
SELECT name,
       CASE 
         WHEN type1 = 'Fire' THEN 'Hot'
         WHEN type1 = 'Water' THEN 'Cool'
         ELSE 'Normal'
       END AS type_description
FROM pokemon;
~~~

> **다음 중 type_description의 결과가 'Normal'로 출력될 포켓몬은?**

| **name**   | **type1** |
| ---------- | --------- |
| Pikachu    | Electric  |
| Charmander | Fire      |
| Squirtle   | Water     |
| Bulbasaur  | Grass     |

<!-- 근거와 함께 답을 작성해주세요 -->

~~~
여기에 답을 작성해주세요!
~~~



<br>

### 🎉 수고하셨습니다.
