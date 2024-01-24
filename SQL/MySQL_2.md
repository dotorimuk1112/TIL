# MySQL_2

분류: SQL

# ✅ 함수

## 숫자형 함수

| 함수 | 설명 | 예시 |
| --- | --- | --- |
| ABS(x) | 숫자의 절대값을 반환 | ABS(-5) → 5 |
| CEIL(x), CEILING(x) | 숫자를 올림 | CEIL(5.3) → 6, CEILING(5.3) → 6 |
| FLOOR(x) | 숫자를 내림 | FLOOR(5.8) → 5 |
| ROUND(x, d) | 숫자를 반올림 | ROUND(5.678, 2) → 5.68 |
| TRUNCATE(x, d) | 숫자를 지정된 소수 자릿수로 절삭 | TRUNCATE(5.678, 2) → 5.67 |
| SQRT(x) | 숫자의 제곱근을 반환 | SQRT(25) → 5 |
| POW(x, y), POWER(x, y) | x의 y제곱을 반환 | POW(2, 3) → 8, POWER(2, 3) → 8 |
| EXP(x) | e의 x승을 반환 | EXP(1) → 2.71828 |
| LOG(x), LN(x) | 자연로그를 반환 | LOG(10) → 2.30259, LN(10) → 2.30259 |
| LOG10(x) | 10을 밑으로 하는 로그를 반환 | LOG10(100) → 2 |
| RAND() | 0과 1 사이의 난수를 반환 | RAND() → 0.12345 (랜덤 값) |
| MOD(x, y) | x를 y로 나눈 나머지를 반환 | MOD(10, 3) → 1 |
| SIGN(x) | 숫자의 부호를 반환 | SIGN(-5) → -1, SIGN(5) → 1, SIGN(0) → 0 |
| ROUND(x) | 가장 가까운 정수로 반올림 | ROUND(5.3) → 5, ROUND(5.8) → 6 |
| TRUNC(x) | 소수 부분을 버림 | TRUNC(5.789) → 5 |
| GREATEST(x, y, ...) | 주어진 값 중 가장 큰 값을 반환 | GREATEST(5, 8, 3) → 8 |
| LEAST(x, y, ...) | 주어진 값 중 가장 작은 값을 반환 | LEAST(5, 8, 3) → 3 |
| DIV(x, y) | x를 y로 나눈 몫을 반환 | DIV(10, 3) → 3 |

## 문자열 함수

| 함수 | 설명 | 예시 |
| --- | --- | --- |
| CONCAT(str1, str2, ...) | 문자열을 결합 | CONCAT('Hello', ' ', 'World') → 'Hello World' |
| CONCAT_WS(separator, str1, ...) | 문자열을 지정된 구분자로 결합 | CONCAT_WS(', ', 'Apple', 'Banana', 'Orange') → 'Apple, Banana, Orange' |
| LENGTH(str), CHAR_LENGTH(str) | 문자열의 길이 (바이트 또는 문자 수) | LENGTH('Hello') → 5, CHAR_LENGTH('안녕하세요') → 5 |
| UPPER(str), LOWER(str) | 대문자 또는 소문자로 변환 | UPPER('hello') → 'HELLO', LOWER('HELLO') → 'hello' |
| LEFT(str, len), RIGHT(str, len) | 문자열의 왼쪽 또는 오른쪽 일부를 반환 | LEFT('Hello', 3) → 'Hel', RIGHT('Hello', 2) → 'lo' |
| SUBSTRING(str, pos, len) | 문자열의 일부를 반환 | SUBSTRING('Hello', 2, 3) → 'ell' |
| REPLACE(str, from_str, to_str) | 문자열에서 특정 부분을 다른 문자열로 대체 | REPLACE('Hello World', 'Hello', 'Hi') → 'Hi World' |
| LPAD(str, len, pad_str) | 문자열을 왼쪽으로 특정 문자로 채움 | LPAD('5', 3, '0') → '005' |
| RPAD(str, len, pad_str) | 문자열을 오른쪽으로 특정 문자로 채움 | RPAD('5', 3, '0') → '500' |
| REVERSE(str) | 문자열을 역순으로 변환 | REVERSE('Hello') → 'olleH' |
| LOCATE(substr, str [, pos]) | 문자열에서 부분 문자열의 위치 검색 | LOCATE('lo', 'Hello') → 4 |
| REPEAT(str, count) | 문자열을 특정 횟수만큼 반복 | REPEAT('A', 3) → 'AAA' |
| LEFT(str, len), RIGHT(str, len) | 문자열의 왼쪽 또는 오른쪽 일부를 반환 | LEFT('Hello', 3) → 'Hel', RIGHT('Hello', 2) → 'lo' |
| FORMAT(number, decimals) | 숫자를 형식화하여 문자열로 반환 | FORMAT(12345.6789, 2) → '12,345.68' |

## 집계 함수

| 함수 | 설명 | 예시 |
| --- | --- | --- |
| COUNT(expr) | 행의 수를 세거나 특정 열의 값의 수를 세는 함수 | COUNT(*), COUNT(column_name) |
| SUM(expr) | 특정 열의 값의 합을 계산 | SUM(sales) |
| AVG(expr) | 특정 열의 값의 평균을 계산 | AVG(price) |
| MIN(expr) | 특정 열의 최솟값을 반환 | MIN(age) |
| MAX(expr) | 특정 열의 최댓값을 반환 | MAX(salary) |
| GROUP_CONCAT(expr) | 그룹 내에서 특정 열의 값을 문자열로 결합 | GROUP_CONCAT(product_name ORDER BY price ASC) |

## 윈도우 함수

| 함수 | 설명 | 예시 |
| --- | --- | --- |
| ROW_NUMBER() | 각 행에 고유한 번호를 부여 | SELECT ROW_NUMBER() OVER (ORDER BY column_name) FROM table; |
| RANK() | 순위를 계산하며, 동일한 값이 있을 경우 동일한 순위 부여 | SELECT RANK() OVER (ORDER BY column_name) FROM table; |
| DENSE_RANK() | 순위를 계산하며, 동일한 값이 있을 경우 동일한 순위 부여하고 다음 값은 건너뛰지 않음 | SELECT DENSE_RANK() OVER (ORDER BY column_name) FROM table; |
| LEAD(col, n [, default]) | 현재 행의 n 번째 다음 행의 값을 가져옴 | SELECT col, LEAD(col, 1) OVER (ORDER BY order_date) AS next_value FROM table; |
| LAG(col, n [, default]) | 현재 행의 n 번째 이전 행의 값을 가져옴 | SELECT col, LAG(col, 1) OVER (ORDER BY order_date) AS prev_value FROM table; |
| SUM(col) OVER (PARTITION BY partition_col ORDER BY order_col) | 파티션 내에서 순서에 따른 누적 합계를 계산 | SELECT col, SUM(col) OVER (PARTITION BY partition_col ORDER BY order_col) FROM table; |
| AVG(col) OVER (PARTITION BY partition_col ORDER BY order_col) | 파티션 내에서 순서에 따른 평균을 계산 | SELECT col, AVG(col) OVER (PARTITION BY partition_col ORDER BY order_col) FROM table; |

## Date_Format 식별자 목록

| 식별자 | 설명 | 예시 |
| --- | --- | --- |
| %Y | 연도(4자리) | 2024 |
| %y | 연도(2자리) | 24 |
| %m | 월(01 ~ 12) | 03 |
| %c | 월(1 ~ 12) | 3 |
| %d | 일(01 ~ 31) | 15 |
| %e | 일(1 ~ 31) | 5 |
| %H | 시간(00 ~ 23) | 14 |
| %h | 시간(01 ~ 12) | 03 |
| %I | 시간(01 ~ 12) | 03 |
| %i | 분(00 ~ 59) | 45 |
| %s | 초(00 ~ 59) | 30 |
| %p | AM 또는 PM | PM |
| %W | 요일 전체 이름 | Friday |
| %a | 요일 축약 이름 | Fri |
| %M | 월 이름 | March |
| %b | 월 축약 이름 | Mar |

# ✅ 조인(Join)