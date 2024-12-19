# GROUP BY

### 1. Contare quanti iscritti ci sono stati ogni anno
``` sql
SELECT COUNT(*) AS `enrolment_count_year`, YEAR(`enrolment_date`) AS `enrolment_year`
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```