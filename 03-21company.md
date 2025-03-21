# HR 데이터베이스 스키마 정리

## 📌 employees (사원 테이블)
| 컬럼명            | 설명                                      | 키 정보       |
|------------------|--------------------------------------|------------|
| `employee_id`    | 사원 ID (기본 키)                    | `PRIMARY KEY` |
| `first_name`     | 사원 이름                             |            |
| `last_name`      | 성(가문)                             |            |
| `email`         | 이메일                                |            |
| `phone_number`   | 전화번호                             |            |
| `hire_date`      | 입사일자                             |            |
| `job_id`        | 업무 ID (`JOBS` 테이블 참조)         | `FOREIGN KEY` |
| `salary`        | 급여                                  |            |
| `commission_pct` | 커미션 퍼센트                        |            |
| `manager_id`     | 상사의 사원 ID (`employees` 참조)   | `FOREIGN KEY` |
| `department_id`  | 부서 ID (`departments` 참조)       | `FOREIGN KEY` |

---

## 📌 departments (부서 테이블)
| 컬럼명           | 설명                                   | 키 정보       |
|-----------------|----------------------------------|------------|
| `department_id`  | 부서 ID (기본 키)                   | `PRIMARY KEY` |
| `department_name` | 부서명                              |            |
| `manager_id`     | 부서 관리자 사원 ID (`employees` 참조) | `FOREIGN KEY` |
| `location_id`    | 위치 ID (`locations` 참조)         | `FOREIGN KEY` |

---

## 📌 locations (위치 테이블)
| 컬럼명           | 설명                    | 키 정보       |
|-----------------|----------------------|------------|
| `location_id`   | 위치 ID (기본 키)      | `PRIMARY KEY` |
| `street_address` | 도로명 주소             |            |
| `postal_code`   | 우편번호                |            |
| `city`         | 도시명                  |            |
| `state_province`| 주(Province)            |            |
| `country_id`    | 국가 ID (`countries` 참조) | `FOREIGN KEY` |

---

## 📌 countries (국가 테이블)
| 컬럼명         | 설명             | 키 정보       |
|--------------|---------------|------------|
| `country_id` | 국가 ID (기본 키) | `PRIMARY KEY` |
| `country_name` | 국가명           |            |
| `region_id`   | 지역 ID (`regions` 참조) | `FOREIGN KEY` |

---

## 📌 regions (지역/대륙 테이블)
| 컬럼명        | 설명       | 키 정보       |
|-------------|---------|------------|
| `region_id` | 지역 ID (기본 키) | `PRIMARY KEY` |
| `region_name` | 지역명     |            |

---

## 📌 jobs (직무 테이블)
| 컬럼명       | 설명         | 키 정보       |
|------------|-----------|------------|
| `job_id`   | 직무 ID (기본 키) | `PRIMARY KEY` |
| `job_title` | 직무명       |            |
| `min_salary` | 최저 급여    |            |
| `max_salary` | 최대 급여    |            |

---

## 🔗 **테이블 간 관계**
- `employees.department_id` → `departments.department_id`
- `employees.manager_id` → `employees.employee_id`
- `employees.job_id` → `jobs.job_id`
- `departments.manager_id` → `employees.employee_id`
- `departments.location_id` → `locations.location_id`
- `locations.country_id` → `countries.country_id`
- `countries.region_id` → `regions.region_id`

---

### 📌 **요약**
이 데이터베이스 스키마는 사원, 부서, 위치, 국가, 지역, 직무 등의 정보를 저장하며,  
각 테이블은 **외래 키(Foreign Key)** 관계를 통해 연결됩니다.  
이를 통해 **조직 내 인사 관리 시스템**을 구성할 수 있습니다. 🚀
