# SQL_BASIC 4주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_4th_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**4주차 과제부터는 강의 내용을 정리하는 것과 함께, 프로그래머스에서 제공하는 SQL 문제를 직접 풀어보는 실습도 병행합니다.** 강의에서는 **배운 내용을 정리하고 주요 쿼리 예제를 정리**하며, 프로그래머스 문제는 **직접 풀어본 뒤 풀이 과정과 결과, 배운 점을 함께 기록**해주세요. 완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**(수행 인증샷은 필수입니다.)** 

## SQL_BASIC_4th

### 섹션 4. 쿼리 잘 작성하기, 쿼리 작성 템플릿 및 오류를 잘 디버깅하기

### 3-4. 오류를 잘 디버깅하는 방법



## 섹션 5. 데이터 탐색 - 변환

### 4-1. INTRO

### 4-2. 데이터 타입과 데이터 변환(CAST, SAFE_CAST)

### 4-3. 문자열 함수(CONCAT, SPLIT, REPLACE, TRIM, UPPER)

### 4-4. 날짜 및 시간 데이터 이해하기(1) (타임존, UTC, Millisecond, TIMESTAMP/DATETIME)



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | ✅         |
| 4주차 | 섹션 **3-4** ~ **4-4** | ✅         |
| 5주차 | 섹션 **4-4** ~ **4-9** | 🍽️         |
| 6주차 | 섹션 **5-1** ~ **5-7** | 🍽️         |
| 7주차 | 섹션 **6-1** ~ **6-6** | 🍽️         |

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념정리

## 3-4. 오류를 디버깅하는 방법

~~~
✅ 학습 목표 :
* 오류의 정의에 대해 설명할 수 있다. 
* 오류 메시지를 보고 디버깅이라는 과정을 수행할 수 있다. 
~~~
1. 오류의 정의
   - "방황하다, 길을 잃다"라는 뜻으로 라틴어(Errare)에서 유래한 단어
   - 부정확하거나 잘못된 행동을 의미
   - 실수와 동의어인 경우도 있음

  1-1. 오류 메세지가 알려주고자 하는 것
    - 현재 작성한 방식으로 하면 답을 얻을 수 없어요 (길잡이 역할)
    - 이 부분에 문제가 되어요 (문제 진단)

2. 오류 메세지를 보고 디버깅해보기


**2-1.**
<img width="1336" height="276" alt="image" src="https://github.com/user-attachments/assets/3d6e3943-cde3-4e34-aa61-ad692b5ce1b2" />
~~~
해석 : 집계 함수 COUNT의 인자 수가 일치하지 않습니다.

=> COUNT() 괄호 안에는 여러가지의 인자가 들어가면 안된다. 오직 하나만 가능
~~~



**2-2.**
<img width="1789" height="430" alt="image" src="https://github.com/user-attachments/assets/0dd8b49e-e71d-4368-ab97-f6327e9fe317" />
~~~
해석 : SELECT 목록 식은 다음에서 그룹화하거나 집계되지 않은 열을 참조합니다.

=> GROUP BY에 적절한 컬럼을 명시하지 않았을 경우 발생하는 오류
~~~

**2-3.**
<img width="1802" height="649" alt="image" src="https://github.com/user-attachments/assets/e43bcf82-df9d-4009-ae96-486db474795b" />
~~~
해석: [8:1] = [줄:칸], 입력이 끝날 것으로 예상되었지만 SELECT 키워드가 입력되었습니다.

=> - SELECT 근처 확인하기
   - 하나의 쿼리엔 SELECT가 1개만 있어야 함
   - 혹은 쿼리가 끝나는 부분에 ; 을 붙이고 실행할 부분만 드래그 앤 드랍해서 실행하기
~~~

**2.4**
<img width="1834" height="525" alt="image" src="https://github.com/user-attachments/assets/b66f85c8-176b-404e-84e1-2ba92d429b84" />
~~~
해석: 입력이 끝날 것으로 예상되었지만 [5:1]에서 키워드 WHERE을 얻었습니다.

=> LIMIT 10을 맨 아래로 옮기거나 삭제를 해준다
~~~

**2-5.**
<img width="1451" height="616" alt="image" src="https://github.com/user-attachments/assets/1c7af8aa-db38-494a-8de0-fe38d48a4448" />
~~~
해석: ")"가 예상되지만 [8:11]에 스크립트가 끝났습니다.

=> 괄호를 작성하지 않은 경우이므로, 괄호를 작성한다.
~~~
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



## 4-2. 데이터 타입과 데이터 변환(CAST, SAFE_CAST)

~~~
✅ 학습 목표 :
* 데이터 타입의 종류를 설명할 수 있다. 
* 데이터 타입을 변환하는 방법을 설명할 수 있다. 
~~~
1. 데이터 타입의 종류

   - 숫자 ex) 1, 2, 3.14
   - 문자 ex) "나", "데이터"
   - 시간, 날짜 ex) 2024-01-01, 2024-01-01 23:59:10
   - 부울(Bool) ex) 참/거짓 ex) WHERE 조건 -> TRUE
   - Json, ARRAY 등..
  
2. 데이터 타입을 변환하는 방법

   2-1. 자료 타입 변경하기
      - 자료 타입을 변경하는 함수 => CAST
      - ex) SELECT
             CAST(1 AS STRING) "숫자 1을 문자 1로 변경"
   
      2-1-1. 안전하게 데이터 타입 변경하기 => SAFE_CAST
            - 문자를 숫자로 바꾸는 식의 변환에 실패할 시도를 할 경우, 단순 오류가 아닌 NULL로 반환한다.

   2-2. 수학 함수

<img width="608" height="444" alt="image" src="https://github.com/user-attachments/assets/58379daa-f708-4806-845e-94615edf7a5e" />

- Tip) 나누기를 할 경우 x/y 대신 SAFE_DIVIDE 함수 사용하기
-  x, y.중 하나라도 0인 경우 그냥 나누면 zero error가 발생
- SAFE_DIVIDE(x, y) 

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



## 4-3. 문자열 함수(CONCAT, SPLIT, REPLACE, TRIM, UPPER)

~~~
✅ 학습 목표 :
* 문자열 함수들의 종류를 이해하고 어떠한 상황에서 사용하는지 설명할 수 있다. 
~~~
**<문자열 함수들의 종류>**
~~~
1. CONCAT
   - CONCAT(컬럼1, 컬럼2, ...)

   - 쿼리 예시
   - SELECT
       CONCAT("안녕", "하세요", "!") AS result

     => "안녕하세요"
~~~
~~~
2. SPLIT
  - SPLIT(문자열 원본, 나눌 기준이 되는 문자)

  - 쿼리 예시
  - SELECT
      SPLIT("가, 나, 다, 라", ", ") AS result

    => "가", "나", "다", "라" (배열(ARRAY))
~~~
~~~
3. REPLACE
   - REPLACE(문자열 원본, 찾을 단어, 바꿀 단어)

   - 쿼리 예시
   - SELECT
      REPLACE("안녕하세요", "안녕", "실천") AS result

   => "실천하세요"
~~~
~~~
4. TRIM
   - TRIM(문자열 원본, 자를 단어)

   - 쿼리 예시
   - SELECT
      TRIM("안녕하세요","하세요") AS result

   => "안녕"
~~~
~~~
5. UPPER
   - UPPER(문자열 원본)

   - 쿼리 예시
   - SELECT
      UPPER("abc") AS result

   => "AB"
~~~
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



## 4-4. 날짜 및 시간 데이터 이해하기(1) (타임존, UTC, Millisecond, TIMESTAMP/DATETIME)

~~~
✅ 학습 목표 :
* 날짜 및 시간 데이터 타입과 UTC의 개념을 설명할 수 있다. 
* DATE, DATETIME, TIMESTAMP 에 대해서 설명할 수 있다.
* 시간함수들의 종류와 시간의 차이를 추출하는 방법을 설명할 수 있다. 
~~~

1. 날짜 및 시간 데이터 타입

   1-1. DATE, DATETIME
      - DATE: DATE만 표시하는 데이터 ex) 2023-12-31
      - DATETIME: DATE와 TIME까지 표시하는 데이터, Time Zone 정보 없음. ex)  2023-12-31 14:00:00

   1-2. 타임존
      - GMT: Green Mean Time(한국 시간: GMT +9)
        => 영국의 그리니치 천문대를 기준으로 지역에 따른 시간의 차이르 조정하기 위해 생긴 시간의 구분선
        
      - UTC: Universal Time Coordinated(한국 시간: UTC +9)
      - 타임존이 존재한다 = 특정 지역의 표준 시간대
        => 국제적인 표준 시간, 협정 세계시.

   1-3. TIMESTAMP
      - 시간 도장
      - UTC부터 경과한 시간을 나타내는 값
      - TIME ZONE 정보 있음
      - ex) 2023-12-31 14:00:00 UTC
  
   1-4. millisecond, microsecond
      - millisecond
           - 시간의 단위, 천 분의 1초(1,000ms = 1초)
           - 우리가 아는 초보다 더 짧은 시간 단위
           - 눈을 깜빡이는 시간이 약 100ms
           - 빠른 반응이 필요한 분야에서 사용(초보다 더 정확하게)
           - Millisecond => TIMESTAMP => DATETIME으로 변경해서 사용
       
        - microsecond(us)
             - 1/1,000ms, 1/1,000,000초

2. 시간 함수 적용 
   
- 예시: 1704176819711ms -> 2024-01-02 15:26:59(DATETIME) + 타임존 추가(Asia/Seoul)
  
<img width="872" height="294" alt="image" src="https://github.com/user-attachments/assets/386b0d4a-92c7-4dfa-8987-93b226a8dcbe" />


- TIMESTAMP_MILLIS => TIMESTAMP를 MILLISECOND로 표현한 것
- TIMESTAMP_MICROS => TIMSESTAMP를 MICROSECOND로 표현한 것
- DATETIME(TIMESTAMP_MICROS(~~~~), 타임존(Asia/Seoul) => TIMSTAMP를 DATETIME으로 바꾸는 함수

3. TIMESTAMP와 DATETIME의 차이

<img width="782" height="299" alt="image" src="https://github.com/user-attachments/assets/fa06282f-8140-41da-bae5-28d161d1bf26" />

   
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



<br>

<br>

---

<img width="392" height="552" alt="image" src="https://github.com/user-attachments/assets/ddaf4d55-372f-4cbb-90ad-24b15119b967" />


# 2️⃣ 확인문제 & 문제 인증

## 프로그래머스 문제 

> 조건에 맞는 회원 수 구하기 (SELECT, COUNT) 
>
> **먼저 문제를 풀고 난 이후에 확인 문제를 확인해주세요**
>
> 문제 링크 
>
> :  https://school.programmers.co.kr/learn/courses/30/lessons/131535#

<!-- 문제를 풀기 위하여 로그인이  필요합니다. -->

<!-- 정답을 맞추게 되면, 정답입니다. 라는 칸이 생성되는데 이 부분을 캡처해서 이 주석을 지우시고 첨부해주시면 됩니다. --> 



## 문제 1

> **🧚Q. 프로그래머스 문제를 풀던 서현이는 여러 번의 시행착오 끝에 결국 혼자 해결하기 어려워 오류 메시지를 공유하며 도움을 요청했습니다. 여러분들이 오류 메시지를 확인하고, 해당 SQL 쿼리에서 어떤 부분이 잘못되었는지 오류 메시지를 해석하고 찾아 설명해주세요.**

~~~sql
# 조건에 맞는 회원 수 구하기 (SELECT, COUNT) 
# 서현이의 SQL 첫 번째 풀이
SELECT COUNT(AGE, JOINED)
FROM USER_INFO
WHERE AGE BETWEEN 20 AND 29
  AND JOINED BETWEEN '2021-01-01' AND '2021-12-31';
  
오류 메시지 : Error: Number of arguments does not match for aggregate function COUNT
 
# 수정하고 난 이후 두 번째 풀이
SELECT AGE, COUNT(*)
FROM USER_INFO
WHERE AGE BETWEEN 20 AND 29
  AND JOINED BETWEEN '2021-01-01' AND '2021-12-31';
  
오류 메시지 : SELECT list expression references column AGE which is neither grouped nor aggregated
~~~



~~~
여기에 답을 작성해주세요!
~~~



### 🎉 수고하셨습니다.
