# SQL_BASIC 2주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_2nd_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**2주차 과제**는 1주차 과제처럼 SQL의 필요성이나 느낀점 위주가 아닌, **실제 강의 내용을 바탕으로 개념을 정리하고 학습한 내용을 집중적으로 기록**해주세요. 완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요. 

**👀(수행 인증샷은 필수입니다.)** 

## SQL_BASIC_2nd

### 섹션 3. 데이터 탐색 - 조건, 추출, 요약

### 2-3. 데이터 탐색 (SELECT, FROM, WHERE)

### 2-4. SELECT 연습문제

### 2-5. 집계 (Group By + Having + Sum/Count)



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | 🍽️         |
| 4주차 | 섹션 **3-4** ~ **4-4** | 🍽️         |
| 5주차 | 섹션 **4-4** ~ **4-9** | 🍽️         |
| 6주차 | 섹션 **5-1** ~ **5-7** | 🍽️         |
| 7주차 | 섹션 **6-1** ~ **6-6** | 🍽️         |

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념정리 

## 2-3. 데이터 탐색 (SELECT, FROM, WHERE)

~~~
✅ 학습 목표 :
* SQL 쿼리 구조를 이해할 수 있다. 
* SELECT, FROM, WHERE의 핵심 문법을 설명할 수 있다. 
~~~

1. SELECT
   -   테이블의 어떤 칼럼을 선택(출력)할때 사용
   -   Table에 저장되어 있는 컬럼 선택 (여러 컬럼 명시 가능)
     ex) Col1 AS new_name
         Col2
      
2. FROM (Dataset.Table) : 어떤 테이블에서 데이터를 확인할 것인가?
   - 데이터를 확인할 Table 명시
   - 이름이 너무 길다면 AS "별칭"으로 별칭 지정 가능
     
4. WHERE: 조건을 붙일때 원하는 조건을 달 때 사용 (type1 = "Fire")
   - FROM에 병시된 Table에 저장된 데이터를 필터링(조건 설정)
   - Table에 있는 컬럼을 조건 설정
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->


## 2-5. 집계 (Group By / HAVING / SUM,COUNT)

~~~
✅ 학습 목표 :
* 데이터를 집계하고 그룹화하는 방법을 설명할 수 있다.
* GROUP BY, HAVING, ORDER BY, 집계함수(SUM/COUNT 등)을 활용하는 방법을 설명할 수 있다.
* having과 where의 차이에 대해서 설명할 수 있다.
~~~
1. GROUP BY : 같은 값끼리 모아서 그룹화한다
   - 특정 컬럼을 기준으로 모으면서 다른 컬럼에선 집계 가능(합, 평균, MAX, MIn 등)
     
2. WHERE과 HAVING의 차이점

   2-1. WHERE: Raw Data인 테이블 데이터 에서 조건 설정

   2-2. HAVING: GROUP BY한 후 조건을 설정하고 싶은 경우 사용

* 서브쿼리를 작성하고, 서브 쿼리 바깥에서 WHERE 조건을 설정하는 것
  = 서브 쿼리에서 HAVING으로 하는 것

3. ORDER BY: 순서 정렬하기
   - 쿼리 맨 마지막에 두고, 쿼리의 맨 마지막에만 작성하면 됨
   - DESC(내림차순), OSC(오름차순 - 보통 Default)
  
4. LIMT : 출력 개수 제한하기 
   - 쿼리문 결과 Row 수를 제한하고 싶은 경우 LIMIT 사용
   - 쿼리문 제일 마지막에 작성
<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



# 2️⃣ 학습 인증란

<img width="974" height="862" alt="image" src="https://github.com/user-attachments/assets/5f38eb94-f6b3-4677-830a-751247063488" />



<br><br>



---

# 3️⃣ 확인문제

## 문제 1

> **🧚Q. 포켓몬 마스터 승화는 포켓몬 데이터 조회하는 SQL문에 재미를 느껴서 혼자서 데이터를 조회하는 쿼리문을 짰습니다. 하지만 세 가지의 오류로 다음 코드가 실행이 안된다고 하는데, 각 오류의 위치와 이유를 설명하고, 올바른 쿼리문으로 수정해보세요.**

~~~sql
# 승화의 SQL Query문 
SELECT name AS '포켓몬 이름', ID;
WHERE type = 'Electric';
FROM pokemon;
~~~



~~~
1. SELECT, FROM, WHERE 순으로 작성해야함
2. 별칭을 지어줄때는 ''안에 이름을 넣으면 안된다.
3. ;를 문장 끝에 작성하면, 또 다른 쿼리문을 작성하는 것으로 인식되므로 빼준다.

=>
SELECT
name AS 포켓몬 이름, id
FROM pokemon
WHERE type = 'Electric'
~~~



## 문제 2

> **🧚Q. 앞서 SQL Query의 오류를 해결한 승화는 기분 좋게 이번에는 포켓몬 데이터에서 타입별 평균 공격력이 60 이상인 타입만 조회하려는 쿼리를 작성하려고 했습니다. 하지만 이번에도 실수를 하여 쿼리문이 실행되지 않거나 잘못된 결과가 나오고 있는데, 쿼리에서 잘못된 부분이 무엇인지 설명하고, 올바르게 수정한 쿼리를 작성해보세요.**

~~~sql
SELECT type, AVG(attack) AS avg_attack
FROM pokemon
WHERE AVG(attack) >= 60
GROUP BY type;
~~~



~~~
1. 평균 공격력을 구한(GROUP BY) 서브 쿼리에서 조건을 확인하고 싶을때는 WHERE이 아닌 HAVING을 써야한다.

SELECT
type,
AVG(attack) AS avg_attack
FROM Pokemon
GROUP BY type
HAVING avg_attack >= 60;

~~~



### 🎉 수고하셨습니다.
