# SQL_BASIC 7주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_7th_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**7주차 과제는 강의 내용을 정리하는 것과 함께, 프로그래머스에서 제공하는 SQL 문제를 직접 풀어보는 실습도 병행합니다.** 강의에서는 **배운 내용을 정리하고 주요 쿼리 예제를 정리**하며, 프로그래머스 문제는 **직접 풀어본 뒤 풀이 과정과 결과, 배운 점을 함께 기록**해주세요. 완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**(수행 인증샷은 필수입니다.)** 

**(마지막 주차입니다. 조금만 더 힘내주세요~!!!)**

## SQL_BASIC_7th

### 섹션 7 데이터 결과 검증, 가독성 있는 쿼리 작성하기

### 6-1. Intro

### 6-2. 가독성을 챙기기 위한 SQL 스타일 가이드

### 6-3. 가독성을 챙기기 위한 WITH 문 & 파티션

### 6-4. 데이터 결과 검증 정의

### 6-5. 데이터 결과 검증 예시

### 6-6. 정리 



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | ✅         |
| 4주차 | 섹션 **3-4** ~ **4-4** | ✅         |
| 5주차 | 섹션 **4-4** ~ **4-9** | ✅         |
| 6주차 | 섹션 **5-1** ~ **5-7** | ✅         |
| 7주차 | 섹션 **6-1** ~ **6-6** | ✅         |

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념정리

## 6-2. 가독성을 챙기기 위한 SQL 스타일 가이드

~~~
✅ 학습 목표 :
* 데이터 결과 검증하기 전에 실수가 발생하는 원인을 설명할 수 있다.
* SQL 쿼리를 가독성 있게 작성할 수 있다. 
~~~


~~~
1. 실수가 잘 발생하는 경우

  - 문법을 잘못 알고 있는 경우
  - 데이터를 파악하지 않고 쿼리를 작성하는 경우
  - 쿼리가 복잡한 경우

2. SQL의 가독성을 위한 가이드

  2-1. 예약어는 대문자로작성
      - 예약어: SELECT, FROM, WHERE, 각종 함수

  2-2. 칼럼 이름은 snake_case로 작성
      - 칼럼 이름은 camelcase가 아닌 snake_case로 작성
      - 둘 중 일관성을 유지하는게 중요

  2-3. 명시적 vs 암시적인 이름
      - Alias로 별칭을 지을 때는 명시적인 이름을 적용한다.
      - AS a, AS b와 같은거 지양
      - JOIN에서는 예외..

  2-4. 왼쪽 정렬
      - 기본적으로 왼쪽 정렬을 기준으로 작성
      - ex) SELECT 다음 줄에 칼럼명 작성

  2-5. 예약어나 컬럼은 한 줄에 하나씩 권장
      - 컬럼은 바로 주석처리할 수 있는 장점이 있기에 한 줄에 하나식 작성

  2-6. 쉼표는 컬럼 바로 뒤에
      - 빅쿼리는 마지막 쉼표를 무시해서 뒤에 작성해도 무방
      - 줄을 맞추기 위해서 바로 뒤가 좋으나 역시 일관성이 중요
~~~
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



## 6-3. 가독성을 챙기기 위한 WITH문 & 파티션

~~~
✅ 학습 목표 :
* SQL 쿼리를 가독성 있게 작성할 수 있다. 
* WITH문과 파티션을 활용해서도 가독성을 챙길 수 있다. 
~~~



<img width="914" height="423" alt="image" src="https://github.com/user-attachments/assets/c7fb53b5-a9e0-4cfe-90c4-3e5312311ef1" />


~~~
1. WITH 구문이란?
  - CTE(Common Table Expression)라고 표현
  - SELECT 구문에 이름을 정해주는 것과 유사
  - 쿼리 내에서 반복적으로 사용할 수 있음
~~~

<img width="608" height="901" alt="image" src="https://github.com/user-attachments/assets/1bcf5be2-1834-4f8c-88b2-e15bf3974659" />

~~~
2. WITH 구문 사용 방법
  - WITH를 통해 쿼리문의 이름을 미리 붙여주고
  - FROM 에 명시적 이름을 통해 불러올 수 있다.
  - 복잡한 서브 쿼리를 단편화 하기 용이
~~~



~~~
3. PARTITION을 사용하면 좋은 점
  1) 쿼리 성능 향상
    - 전체 데이터를 스캔하는 것보다 파티션을 설정한 곳만 스캔하는 것이 더 빠름

  2) 데이터 관리 용이성
    - 특정 일자의 데이터를 모두 변경하거나 삭제해야 하면 파티션을 설정해서 삭제할 수 있음

  3) 비용
    - 파티션에 해당되는 데이터만 스캔해서 비용을 줄일 수 있음
      (BigQuery는 쿼리 용량에 비례해서 과금하기 때문)\
~~~



<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



## 6-4. 데이터 결과 검증 정의 

~~~
✅ 학습 목표 :
* 데이터 결과 검증이 어떤 과정인지 설명할 수 있다. 
* 데이터 결과 검증에 대한 예시를 이해할 수 있다.  
~~~

~~~
1. 데이터 결과 검증의 정의
  - SQL 쿼리 후 얻은 결과가 예상고하 일치하는지 확인하는 과정
  - 목적: 분석 결과의 정확성, 신뢰성 확보

2. 데이터 검증 방법
  - 내가 기대하는 예상 결과를 정의
  - 쿼리 작성
  - 두개가 일치하는지 비교

3. 제일 중요한 부분
  - 문제를 잘 정의하고, 미리 작성해보기
  - 도메인 특수성(이런 규칙 등) 잘 파악하기 (계약 정산 비율)
~~~


<img width="955" height="533" alt="image" src="https://github.com/user-attachments/assets/d884d030-4f67-4be4-bd3c-5f2050368e55" />

~~~
- 데이터 결과를 검증하는 흐름
~~~


~~~
4. 데이터 결과 검증할 때 자주 활용하는 SQL 쿼리

  1) COUNT(*): 행 수를 확인. 의도한 데이터의 행 개수가 맞는가?

  2) NOT NULL: 특정 컬럼에 NULL이 존재하는가? 필수 필드가 비어있지 않는가?

  3) DISTINCT: 데이터의 고유값을 확인해 중복 여부 확인

  4) IF문, CASE WHENL: 의도와 같다면 TRUE, 아니면 FALSE

1) + 3)
 => SELECT COUNT(DISTINCT col), COUNT(dol) 두 칼럼을 보고 개수를 비교


5. 데이터 결과 검증을 할 때 활용하는 방식

  1) 특정 user_id로 필터링을 걸어서 확인
    - 1명의 데이터를 확인 (예: WHERE user_id = 402)
    - 결과를 예상할 때 Raw 데이터에서 하나씩 눈으로 세고 적어둠(예상 결과)
    - 1명의 데이터의 예상 결과와 쿼리 결과가 동일한지 확인
    - 다른 user_id 3~4건 더 추가해서 확인 (여러케이스 존재 가능)
    - 3~4개에서 동일한 결과가 나오면 user_id 조건 삭제
~~~


<img width="528" height="353" alt="image" src="https://github.com/user-attachments/assets/40da4b77-5591-45f6-88d2-8bffe5629395" />



~~~
  2) 샘플 데이터 생성하기
    - WITH 문을 사용해 예시 데이터를 생성한 후, 결과를 예상하고 쿼리 작성
    - 복잡한 데이터에서 하기 전에, 쿼리 자체가 올바른지 확인할 때 주로 사용
~~~







<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->





<br>
<img width="391" height="577" alt="image" src="https://github.com/user-attachments/assets/d39a336b-abbb-4c03-9a27-8aab282c94a5" />

<br>

---

# 2️⃣ 확인문제 & 문제 인증

## 프로그래머스 문제 

https://school.programmers.co.kr/learn/courses/30/lessons/157343

> 특정 옵션이 포함된 자동차 리스트 구하기

<img width="1919" height="907" alt="image" src="https://github.com/user-attachments/assets/ce5f473d-764b-46df-b050-0c0412aa770e" />


~~~
1번 문제: 오답

- WHERE 절에 OPTIONS = '네비게이션' 만 함
- 이럴 경우 오직 네비게이션만 옵션으로 갖고 있는 데이터만 출력이 됨.
- LIKE '%네비게이션% 을 WHEHE 절에 걸어줘서 앞, 가운데, 뒤에 네비게이션이 들어가는 경우를 모두 찾아줘야함
- 콤마로 구분된 키워드 리스트 이기 때문에
~~~


https://school.programmers.co.kr/learn/courses/30/lessons/59044

> 오랜 기간 보호한 동물(1) 


<img width="1919" height="910" alt="image" src="https://github.com/user-attachments/assets/14bf168e-e8b5-415f-aa01-5f5774df0a69" />


~~~
2번 문제: 오답

- LEFT JOIN을 통해 ANIMAL_OUTS의 값이 NULL일 경우 입양이 되지 않는 조건일 것이라는 생각은 함
- 그러나 이를 어떻게 해야할지 몰랐음.
- LEFT JOIN을 한후 그냥 WHERE절에 ANIMAL_OUTS의 JOIN 키의 값이 NULL이면 됨.
- 그러나 어떤 것이 NULL이라고 해야할지 몰랐음
- 이후 DATETIME의 순서를 조건을 걸어서 하려고함
- 그냥 ASC를 통해 LIMIT 3을 걸면 됨.
~~~



https://school.programmers.co.kr/learn/courses/30/lessons/59043

> 있었는데요 없었습니다.


<img width="1920" height="906" alt="image" src="https://github.com/user-attachments/assets/f8b9e2ae-8c08-4bc7-a2c9-6412c42ef6e5" />



~~~
3번 문제: 정답

답:
SELECT
 I.ANIMAL_ID,
 I.NAME
FROM ANIMAL_INS AS I
LEFT JOIN ANIMAL_OUTS AS O
ON I.ANIMAL_ID = O.ANIMAL_ID
WHERE
 I.DATETIME > O.DATETIME
ORDER BY
 I.DATETIME ASC;

- 날짜가 빠르다? -> 많다 크다?? 의 개념이 헷갈렸음
- 늘 틀리는 것 => SELECT와 FROM 사이에 조인을 했을 경우 어떤 조인의 컬럼을 불러올것인지 명시해줘야함
~~~


## LeetCode 문제

https://leetcode.com/problems/combine-two-tables/description/

> 175. Combine Two Tables

<img width="917" height="709" alt="image" src="https://github.com/user-attachments/assets/f93ee333-cc45-4697-8978-2ceecf2ec4c6" />




https://leetcode.com/problems/list-the-products-ordered-in-a-period/

> 1327. List the Products Ordered in a Period

<img width="861" height="776" alt="image" src="https://github.com/user-attachments/assets/e3160221-2e83-434a-8cf9-46492eaddeb8" />


~~~
2번 문제: 오답

- unit이 100이상이라는게 무슨말인지 이해를 못함
- total unit이 100이상이라는 것이니까 HAVING을 통해 전체 조건을 걸고 unit >= 100 이라고 하면 됨.
- 2020 2월을 어떻게 조건을 걸어야할지 막힘.. 항상 DATE만 들어가도 뇌가 멈추는 듯..
- WHERE절을 o.order_date >= '2020-02-01' AND o.order_date < '2020-03-01' 이런식으로 걸어주면 끝
~~~
<!-- 정답을 맞추게 되면, 정답입니다. 이 부분을 캡처해서 이 주석을 지우시고 첨부해주시면 됩니다. --> 



## 문제 1

> **🧚예운이는 다음 SQL 쿼리를 다트비 정규과제에 제출했다. 제출한 쿼리는 다음과 같고, 이 쿼리는 에러 메시지 없이 잘 수행하는 쿼리이다.**

~~~sql
# 주영이가 작성한 가독성 나쁜 SQL 

select u.name , o.OrderID
, p.ProductName ,od.Quantity ,od.UnitPrice 	from Users u	join Orders o on u.id = o.userId
join OrderDetails od on o.OrderID = od.orderID	join Products p on od.ProductID = p.ProductID
where u.region= 'Busan'			order by o.OrderID
~~~

> **이에 과제를 검사하던 정우는 작성한 SQL을 보고 코드 리뷰를 진행하려고 했지만, 다음 쿼리를 보고 예운이에게 질문을 하였다. "예운아, 이 쿼리 가독성이 좀 안 좋은데 내가 고쳐도 괜찮을까? 가독성 좋게 SQL 가이드에 따라 정리해보려고 해"**
>
> 다음 SQL 쿼리를 **가독성 좋은 스타일로 다시 작성해보세요.** 



~~~
여기에 답을 작성해주세요.
~~~



<br>

<br>

<!-- 이렇게 SQL BASIC 과제가 마무리되었습니다. SQL은 범위가 넓고 처음 접할 때 어렵게 느껴지는 학문이지만, 이번 기수에서는 지난 기수에도 활용했던 인프런 무료 강의를 통해 기초를 탄탄히 다질 수 있도록 구성했습니다. 환경 세팅 과정이 다소 복잡했을 수도 있지만, 이번 과제를 통해 기본적인 쿼리 작성과 SELECT 명령어의 개념을 충분히 익혔을 거라 생각합니다. BASIC을 통해 데이터를 추출하는 기초를 다졌으면, 이제 ADVANCED 트랙에서 실무에 맞게 더 복잡한 문접과 분석 쿼리, 그리고 MASTER 트랙에서 실제 데이터베이스를 다루는 실무 명령어까지 배워갈 수 있습니다. 앞으로의 SQL 학습에도 화이팅이고, 부족한 템플릿이었지만 끝까지 함께해줘서 진심으로 감사드립니다.  -->

### 🎉 수고하셨습니다.
