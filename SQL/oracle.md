# oracle spl 

###### Bigdata Iot class (2021/07/28~)

## 오라클 설치 방법



## hr 계정

> * hr 계정



#### hr 계정 사용하는 법

1. 

## select

### 1. select 문의 기본 형식

```sql
SQL> select {컬럼명} from {테이블명};
```

{컬럼명}

* `from` 절의 테이블 안에서 출력할 칼럼명이나, `*`(모든 칼럼 표시)를  `select` 와 `from` 사이에 작성합니다.

  이때, 여러 칼럼을 출력하고 싶을 때는 ,(컴마)로 구분합니다.

  > ```sql
  > SQL> select * from tab;
  > ```
  >
  > ```sql
  > SQL> select employee_id, firsr_name, emali from employees;
  > ```

* 칼럼명 뒤에는 한 칸 이상의 공백을 주거나 " "(큰따옴표) 그리고 `as`를 이용하여  alias(별칭)을 줄 수 있습니다. 

  > ```sql
  > SQL> select firsr_name 이름, hire_date 입사일 from employees;
  > ```
  >
  > ```sql
  > SQL> select firsr_name "이름", hire_date "입사일" from employees;
  > ```
  >
  > ```sql
  > SQL> select firsr_name as 이름, hire_date as 입사일 from employees;
  > ```

* 함수나 연산을 컬럼에 적용할 수 있으며, alias(별칭)에 특수문자나 공백을 포함하고 싶은 경우에는 " "(큰따옴표)로 표시합니다.

  > ```sql
  > SQL> select firsr_name 이름, salary*12 "직원의 연봉" 입사일 from employees;
  > ```

* 연결연산자를 사용해서 여러개의 컬럼을 하나의 컬럼으로 표시할 수 있습니다.

  > ```sql
  > SQL> select firsr_name 이름 ||'의 입사일은 '|| hire_date 입사일 ||'입니다.' from employees;
  > ```

* 칼럼명 앞에 distinct를 이용하면 중복을 제거할 수 있습니다.

  > ```sql
  > SQL> select distinct salary from employees;
  > ```

{테이블명}

* `from` 절에는 찾을 테이블명을 작성합니다.

  > ```sql
  > SQL> select * from tab;
  > ```
  >
  > ```sql
  > SQL> select * from employees;
  > ```

* `from` 절에 사용하는 alias(별칭)는 길고 복잡한 코드를 단순화하기 위하여 사용합니다.

  > ```sql
  > SQL> select e.employee_id, j.job_title from employees e, jobs j;
  > ```



### 2. select문에 where절을 이용해 조건 적용하기

```sql
SQL> select {컬럼명} from {테이블명} where {조건};
```



### 3. select문에 order by절을 이용해 출력 순서 지정하기

```sql
SQL> select {컬럼명} from {테이블명} where {조건} order by {컬럼명}, {정렬방법};
```



### 4. 함수

* ##### 산술연산자

  * 산술연산자의 종류

    | 산술연산자 |  의미  |  표현   |
    | :--------: | :----: | :-----: |
    |     +      | 더하기 | A `+` B |
    |     -      |  빼기  | A `-` B |
    |     *      | 곱하기 | A `*` B |
    |     /      | 나누기 | A `/` B |

    

* ##### 관계연산자

  * 관계연산자의 종류

    | 관계연산자 |       의미        |       표현       |
    | :--------: | :---------------: | :--------------: |
    |     >      |    크다, 초과     |     A `>` B      |
    |     >=     | 크거나 같다, 이상 |     A `>=` B     |
    |     <      |    작다, 미만     |     A `<` B      |
    |     <=     | 작거나 같다, 이하 |     A `<=` B     |
    |     =      |       같다        |     A `=` B      |
    |   <>, !=   | 같지 않다, 아니다 | A `<>` B, A`!=`B |

    

* ##### 논리연산자

  * 논리연산자의 종류

    | 논리연산자 |  의미  |   표현    |
    | :--------: | :----: | :-------: |
    |    AND     | 논리곱 | A `and` B |
    |     OR     | 논리합 | A `or` B  |
    |    NOT     |  부정  | `not`  A  |

    

* ##### 연결연산자

  * `||` 

    연결연산자 `||` (concatenation)은 문자형 자료들을 결합한다.

* ##### like 연산자

  * `like` 
  * `not like` 

* ##### in 연산자

  * `in` 
  * `not in` 

* ##### between and 연산자

  * `between` {min} `and` {max}

* ##### is null 연산자

  * `is null` 
  * `is not null` 



### 5. select문에서 group by절과 그룹 함수

```sql
SQL> select {컬럼명} from {테이블명} where {조건} group by {컬럼명} order by {컬럼명}, {정렬방법};
```



### 6.  select문에 having절을 이용해 조건 적용하기

```sql
SQL> select {컬럼명} from {테이블명} where {조건} group by {컬럼명}  having {조건} order by {컬럼명}, {정렬방법};
```

