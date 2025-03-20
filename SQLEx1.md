# SQL Queries
```sql
- 13. 급여가 1600보다 크고 3000보다 작은 사람의 이름, 직업, 급여 출력
SELECT FIRST_NAME, JOB_ID, SALARY
FROM EMPLOYEES
WHERE SALARY > 1600 AND SALARY < 3000;

-- 14. 사원번호가 7654와 7782 사이 이외의 사원의 모든 정보 출력
SELECT *
FROM EMPLOYEES
WHERE EMP_ID NOT BETWEEN 7654 AND 7782;

-- 16. 입사일이 81년 이외에 입사한 사람의 모든 정보 출력
SELECT *
FROM EMPLOYEES
WHERE EXTRACT(YEAR FROM HIRE_DATE) != 1981;

-- 17. 직업이 MANAGER와 SALESMAN인 사람의 모든 정보 출력
SELECT *
FROM EMPLOYEES
WHERE JOB_ID IN ('MANAGER', 'SALESMAN');

-- 18. 부서번호가 20, 30번을 제외한 모든 사람의 이름, 사원번호, 부서번호 출력
SELECT FIRST_NAME, EMP_ID, DEPARTMENT_ID
FROM EMPLOYEES
WHERE DEPARTMENT_ID NOT IN (20, 30);

-- 19. 이름이 S로 시작하는 사원의 사원번호, 이름, 입사일, 부서번호 출력
SELECT EMP_ID, FIRST_NAME, HIRE_DATE, DEPARTMENT_ID
FROM EMPLOYEES
WHERE FIRST_NAME LIKE 'S%';

-- 20. 입사일이 81년도인 사람의 모든 정보 출력
SELECT *
FROM EMPLOYEES
WHERE EXTRACT(YEAR FROM HIRE_DATE) = 1981;

-- 21. 이름 중 S자가 들어가 있는 사람만 모든 정보 출력
SELECT *
FROM EMPLOYEES
WHERE FIRST_NAME LIKE '%S%';

-- 22. 이름이 S로 시작하고 마지막 글자가 T인 사람의 모든 정보 출력 (단, 이름은 전체 5자리)
SELECT *
FROM EMPLOYEES
WHERE FIRST_NAME LIKE 'S___T';

-- 23. 첫 번째 문자는 관계없고 두 번째 문자가 A인 사람의 정보 출력
SELECT *
FROM EMPLOYEES
WHERE FIRST_NAME LIKE '_A%';

-- 24. 커미션이 NULL인 사람의 정보를 출력
SELECT *
FROM EMPLOYEES
WHERE COMMISSION_PCT IS NULL;

-- 25. 커미션이 NULL이 아닌 사람의 모든 정보 출력
SELECT *
FROM EMPLOYEES
WHERE COMMISSION_PCT IS NOT NULL;

-- 26. 부서가 30번 부서이고 급여가 1500 이상인 사람의 이름, 부서, 월급 출력
SELECT FIRST_NAME, DEPARTMENT_ID, SALARY
FROM EMPLOYEES
WHERE DEPARTMENT_ID = 30 AND SALARY >= 1500;

-- 27. 이름의 첫 글자가 K로 시작하거나 부서번호가 30번인 사람의 사원번호, 이름, 부서번호 출력
SELECT EMP_ID, FIRST_NAME, DEPARTMENT_ID
FROM EMPLOYEES
WHERE FIRST_NAME LIKE 'K%' OR DEPARTMENT_ID = 30;

-- 28. 급여가 1500 이상이고 부서번호가 30번인 사원 중 직업이 MANAGER인 사람의 정보 출력
SELECT *
FROM EMPLOYEES
WHERE SALARY >= 1500 AND DEPARTMENT_ID = 30 AND JOB_ID = 'MANAGER';

-- 29. 부서번호가 30번인 사람 중 사원번호 정렬하라
SELECT *
FROM EMPLOYEES
WHERE DEPARTMENT_ID = 30
ORDER BY EMP_ID;

-- 30. 급여가 많은 순으로 정렬
SELECT *
FROM EMPLOYEES
ORDER BY SALARY DESC;

-- 31. 부서번호로 오름차순 정렬 후 급여 많은 순으로 출력
SELECT *
FROM EMPLOYEES
ORDER BY DEPARTMENT_ID ASC, SALARY DESC;

-- 32. 부서번호로 내림차순 정렬하고 이름순 오름차순, 급여순 내림차순 정렬
SELECT *
FROM EMPLOYEES
ORDER BY DEPARTMENT_ID DESC, FIRST_NAME ASC, SALARY DESC;
```sql