# MySQL_1

분류: SQL
날짜: 2023년 12월 15일

# ✅Database와 기본 개념

<aside>
💡 **데이터베이스**
체계적으로 구조화된 데이터의 집합
특정 목적에 맞게 조직화되고 관리되며, 효율적 관리와 접근을 가능케 한다.

DBMS는 이런 데이터베이스를 관리하는 소프트웨어 시스템
DBMS 중에서도 데이터베이스 간의 관계를 중심으로 관리하는 DBMS를 관계형 데이터베이스 관리 시스템라고 하며, 대표적으로 **MySQL, Oracle** 등이 있다.

</aside>

<aside>
💡 **스키마(Schema)**
테이블, 열, 인덱스, 제약조건 등 데이터베이스의 논리적 구조를 정의
데이터의 타입과 길이, 관계 등을 명시적으로 지정한다.
**DB의 전체적인 논리 구조를 나타내는 개념**

</aside>

<aside>
💡 **테이블(Table)**
행렬 형태의 데이터 테이블.

</aside>

## MySQL 설치와 사용

[MySQL :: Download MySQL Installer (Archived Versions)](https://downloads.mysql.com/archives/installer/)

[Visual Studio Tools 다운로드 - Windows, Mac, Linux용 무료 설치](https://visualstudio.microsoft.com/ko/downloads/)

![Untitled](.\SQL\MySQL_1\Untitled.png)

- Workbench에 접속할 수 있는 화면.
    - 로컬 환경에서 작업할 수 있고, AWS 등 클라우드와 연결하여 작업할 수도 있다

# ✅SQL(Structured Query Language)

<aside>
💡 **SQL**
Structured Query Language의 약자
사람과 DBMS 사이의 소통으로 자료의 처리를 위한 질의 언어
DMBS별로 문법이 상이하지만, 거의 같은 흐름을 보인다.

</aside>

## DDL(Data Definition Language)

<aside>
💡 데이터 정의 언어
데이터베이스의 구조를 정의하고 설명하는 데 쓰이는 언어.
테이블, 관계, 제약 조건 등을 정의한다.

</aside>

- **CREATE**: 테이블, 뷰, 인덱스 등 객체 생성
    
    ```sql
    CREATE TABLE employees (
        employee_id INT PRIMARY KEY, -- id를 primary key로 지정
        first_name VARCHAR(50),
        last_name VARCHAR(50),
        hire_date DATE
    );
    ```
    
- **ALTER**: 테이블이나 다른 데이터베이스 객체의 구조 변경
    
    ```sql
    ALTER TABLE employees
    ADD COLUMN salary DECIMAL(10, 2);
    ```
    
- **DROP**: 테이블, 뷰, 인덱스 등 객체 삭제
    
    ```sql
    DROP TABLE employees;
    ```
    
- **TRUNCATE:** 테이블 구조 유지하고 모든 행 삭제
    
    ```sql
    TRUNCATE TABLE employees;
    ```
    
- **RENAME:** 데이터베이스 객체의 이름을 변경
    
    ```sql
    RENAME TABLE old_table TO new_table;
    ```
    

## DML(Data Manipulation Language)

<aside>
💡 데이터 조작 언어
데이터베이스에 저장된 데이터를 검색하거나 조작하는 데 사용
주로 테이블에 데이터 삽입, 갱신, 삭제, 조회에 사용됨

</aside>

- **SELECT**: 데이터 조회
    
    ```sql
    SELECT * FROM employees WHERE department_id = 1;
    -- employees 테이블에서 department_id가 1인 데이터 모두(*) 조회
    ```
    
- **INSERT**: 테이블에 데이터 추가
    
    ```sql
    INSERT INTO employees (employee_id, first_name, last_name, hire_date)
    VALUES (1, 'John', 'Doe', '2022-01-01');
    ```
    
- **UPDATE**: 테이블의 기존 데이터 갱신
    
    ```sql
    UPDATE employees
    SET salary = 50000
    WHERE employee_id = 1;
    -- employees 테이블의 employee_id가 1인 행의 salary열 50000으로 update
    ```
    
- **DELETE**: 테이블에 특정 조건을 만족하는 데이터 삭제
    
    ```sql
    DELETE FROM employees
    WHERE employee_id = 1;
    employees 테이블에서 employee_id가 1인 행 삭제
    ```
    

## DCL(Date Control Language)

<aside>
💡 데이터 제어 언어
데이터베이스에 대한 액세스 권한을 부여하거나 회수하는 언어
사용자에게 어떤 종류의 작업을 수행할 권한을 부여하거나 박탈하는 데에 사용됨

</aside>

- GRANT: 사용자에게 특정 객체에 대한 권한 부여
    
    ```sql
    GRANT SELECT, INSERT ON employees TO 'user1'@'localhost';
    -- user1에게 employees 테이블에 대해서 SELECT와 INSERT 승인
    ```
    
- REVOKE: 사용자에게 부여된 권한 회수
    
    ```sql
    REVOKE INSERT ON employees FROM 'user1'@'localhost';
    -- user1에게서 employees 테이블에 대해서 INSERT 권한 회수
    ```
    

# ✅데이터 자료형

- 문자형
    
    
    | 데이터 유형 | 설명 | 최대 크기 예시 |
    | --- | --- | --- |
    | CHAR(n) | 고정 길이 문자열 | 항상 n |
    | VARCHAR(n) | 가변 길이 문자열 | 최대 길이 n |
    | TEXT | 긴 문자열 | 최대 65,535 바이트 |
    | ENUM | 열거형 문자열 | 최대 65,535 값 중 하나 |
    | SET | 문자열 집합 | 최대 64 값 중 여러 개 선택 |
- 숫자형
    
    
    | 데이터 유형 | 설명 | 최대 크기 예시 |
    | --- | --- | --- |
    | TINYINT | 매우 작은 정수 | 127 (signed), 255 (unsigned) |
    | SMALLINT | 작은 정수 | 32,767 (signed), 65,535 (unsigned) |
    | MEDIUMINT | 중간 크기 정수 | 8,388,607 (signed), 16,777,215 (unsigned) |
    | INT | 정수 | 2,147,483,647 (signed), 4,294,967,295 (unsigned) |
    | BIGINT | 큰 정수 | 9,223,372,036,854,775,807 (signed), 18,446,744,073,709,551,615 (unsigned) |
    | FLOAT | 단정도 부동 소수점 | (4 바이트) |
    | DOUBLE | 배정도 부동 소수점 | (8 바이트) |
    | DECIMAL | 고정 소수점 | 정밀도 및 스케일에 따라 다름 |
- 날짜형
    
    
    | 데이터 유형 | 설명 | 최대 크기 예시 |
    | --- | --- | --- |
    | DATE | 날짜 | '1000-01-01' ~ '9999-12-31' |
    | TIME | 시간 | '-838:59:59' ~ '838:59:59' |
    | DATETIME | 날짜와 시간 | '1000-01-01 00:00:00' ~ '9999-12-31 23:59:59' |
    | TIMESTAMP | 날짜와 시간 (자동 갱신) | '1970-01-01 00:00:01' UTC ~ '2038-01-19 03:14:07' UTC |
    | YEAR | 년도 | 1901 ~ 2155 |