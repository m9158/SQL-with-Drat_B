# SQL_BASIC 6주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_6th_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**6주차 과제는 강의 내용을 정리하는 것과 함께, 프로그래머스에서 제공하는 SQL 문제를 직접 풀어보는 실습도 병행합니다.** 강의에서는 **배운 내용을 정리하고 주요 쿼리 예제를 정리**하며, 프로그래머스 문제는 **직접 풀어본 뒤 풀이 과정과 결과, 배운 점을 함께 기록**해주세요. 완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**(수행 인증샷은 필수입니다.)** 

## SQL_BASIC_6th

### 섹션 6. 다량의 자료를 연결 : JOIN 

### 5-1. Intro

### 5-2. JOIN 이해하기

### 5-3. 다양한 JOIN 방법

### 5-4. JOIN 쿼리 작성하기 

### 5-5. JOIN을 처음 공부할 때 헷갈렸던 부분

### 5-6. JOIN 연습문제 1~2번

### 5-6. JOIN 연습문제 3~5번

### 5-7. 정리



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | ✅         |
| 4주차 | 섹션 **3-4** ~ **4-4** | ✅         |
| 5주차 | 섹션 **4-4** ~ **4-9** | ✅         |
| 6주차 | 섹션 **5-1** ~ **5-7** | ✅         |
| 7주차 | 섹션 **6-1** ~ **6-6** | 🍽️         |

<!-- 여기까진 그대로 둬 주세요-->

<br>

---

# 1️⃣ 개념정리

## 5-2. JOIN 이해하기

~~~
✅ 학습 목표 :
* JOIN에 대한 정의와 필요성에 대해 설명할 수 있다.
~~~

1. JOIN 이란??
   - 서로 다른 데이터 테이블을 연결하는 것
   - 공통적으로 존재하는 컬럼(=KEY)이 있다면, JOIN 할 수 있음

2. JOIN이 필요한 이유
   - 단일자료를 보는 것이 아니라 다량의 자료를 보기 위해서 데이터간 연결이 필요할 때
   - 관계형 데이터베이스 설계시 정규화 과정을 거침
   - 정규화는 중복을 최소화하게 데이터를 구조화
   - 따라서 데이터를 다양한 table에 저장해서 필요할 때 JOIN해서 사용
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



## 5-3. 다양한 JOIN 방법

~~~
✅ 학습 목표 :
* JOIN 방법들의 종류를 설명할 수 있다. 
* 각 JOIN 방법들의 차이점에 대해서 설명할 수 있다. 
~~~

**<기존 테이블>**


<img width="247" height="214" alt="image" src="https://github.com/user-attachments/assets/5e4ba15f-3287-46e3-9e2c-7c1b2ef0011b" />

- DATE 데이터는 초단위까지 기록되기 때문에 원하는 형식으로 정리하기 위해 DATE_FORMAT을 사용해야함.
~~~
1. (INNER) JOIN
   - 두 테이블의 공통 요소만 연결 
~~~

<img width="322" height="113" alt="image" src="https://github.com/user-attachments/assets/361f162a-38d0-4565-a2bb-653a797e1e5f" />


~~~
2. LEFT/RIGHT (OUTER) JOIN
   - 왼쪽/오른쪽 테이블 기준으로 연결
~~~



<img width="456" height="131" alt="image" src="https://github.com/user-attachments/assets/3b1d3b2a-61ea-401e-b014-49c74dccbece" />      <img width="305" height="127" alt="image" src="https://github.com/user-attachments/assets/4c309f0a-8b47-4159-aff3-e1b776cfb4ed" />




~~~
3. FULL (OUTER) JOIN
   - 양쪽 기준으로 연결
~~~

<img width="469" height="156" alt="image" src="https://github.com/user-attachments/assets/9a5ac557-6e6d-46e0-ae3c-d1ac741a8059" />


~~~
4. CROSS JOIN
   - 두 테이블의 각각의 요소를 곱하기
~~~

<img width="196" height="431" alt="image" src="https://github.com/user-attachments/assets/6628880b-033b-4f2f-b54a-14f549c4b99a" />

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->


## 5-4. JOIN 쿼리 작성하기 

~~~
✅ 학습 목표 :
* JOIN을 사용한 문법에 대해 이해하여 적용할 수 있다.
* JOIN 을 활용한 쿼리를 작성할 수 있다. 
~~~

1. SQL JOIN 문법

<img width="683" height="435" alt="image" src="https://github.com/user-attachments/assets/f433d349-fb61-4ad5-8888-355dfd983973" />

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



## 5-6. JOIN 연습문제 1~5번 

~~~
✅ 학습 목표 :
* 연습문제(3문제 이상) 푼 것들 정리하기
~~~

~~~
문제 2번 : 오답

- trainer_pokemon을 기준 테이블로 잡고 서브쿼리 바깥에서 조건을 걸어줘야함
- 하지만 서브쿼리 안에서 조건을 걸려고 했는데, type1이라는 칼럼이 없다는 것을 확인
- 이후 기준 테이블을 pokemon으로 잡아버림 -> 조건을 서브쿼리 안에 걸어야한다는 집착이 만든 패착.
- 그냥 서브쿼리 바깥에 조건을 걸어주면 되는 문제
~~~


~~~
문제 3번: 오답

- current_health IS NULL을 통해 결측치가 없는지 확인하는 것이 좋음
- 서브쿼리에 대한 강박을 버리기 -> 서브쿼리를 굳이 사용하지 않고 전체를 WHERE절로 묶음
- "hometown" = "location" 으로 작성했는데 t.hometown = tp.location으로 작성했어야함
- COUNT() 가 아니라 DISTINCT를 사용해야지 트레이너 수를 구할 수 있음. 그렇지 않으면 트레이너와 포켓몬이 같은 건수가 합쳐져서 구해짐
~~~


~~~
문제 4번: 오답

- 3번 문제와 똑같은 실수, t.acheivement = "Master"로 해야함
- 마스터인 것 중에서 가장 많은 타입을 2중 조건으로 이해해서 서브쿼리 2개로 WHERE을 두번 쓰려고 했던 것이 패착
- 이후 type1을 집계 할 것이기 때문에 최종 쿼리에 type1을 기재후 tp.id로 카운트 해야함
~~~

~~~
문제 5번: 정답

- 정답인데, 각각 트레이너에서 1세대 몇마리 2세대 몇마리를 구해야해는지로 이해해서 복잡해질 뻔...?
~~~
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



<br>
<img width="389" height="660" alt="image" src="https://github.com/user-attachments/assets/0f56e2a2-e422-465e-8a73-df2e534b817b" />

<br>

---

# 2️⃣ 확인문제 & 문제 인증

## 프로그래머스 문제 

https://school.programmers.co.kr/learn/courses/30/lessons/164673

> 조건에 부합하는 중고거래 댓글 조회하기 (JOIN)

<img width="1890" height="902" alt="image" src="https://github.com/user-attachments/assets/32c300c7-93e6-4613-9ea7-19d1453f93d2" />


https://school.programmers.co.kr/learn/courses/30/lessons/144854

> 조건에 맞는 도서와 저자 리스트 출력하기 (JOIN)

<!-- 정답을 맞추게 되면, 정답입니다. 이 부분을 캡처해서 이 주석을 지우시고 첨부해주시면 됩니다. --> 



---

# 3️⃣ 참고자료

JOIN 에 대해서 그림으로 쉽게 이해할 수 있는 자료들도 있어서 첨부합니다. 아래의 블로그도 학습할 때 같이 참고해주세요.

1. https://data-marketing-bk.tistory.com/entry/SQL-JOIN-%ED%95%9C-%EB%B0%A9%EC%97%90-%EC%A0%95%EB%A6%AC-%EA%B0%9C%EB%85%90%EB%B6%80%ED%84%B0-%EC%BD%94%EB%93%9C%EA%B9%8C%EC%A7%80-%EC%9D%B4%EA%B2%83%EB%A7%8C-%EB%B3%B4%EC%9E%90



2. https://velog.io/@wijoonwu/JOIN

<br>

### 🎉 수고하셨습니다.
