# GROUP BY

### 1. Contare quanti iscritti ci sono stati ogni anno
``` sql
SELECT COUNT(*) AS `enrolment_count_year`, YEAR(`enrolment_date`) AS `enrolment_year`
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```

### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
``` sql
SELECT COUNT(*) AS `same_office_address`, `office_address`
FROM `teachers`
GROUP BY `office_address`
```

### 3. Calcolare la media dei voti di ogni appello d'esame
``` sql
SELECT AVG(`vote`) AS `media_vote`, `student_id`
FROM `exam_student`
GROUP BY `student_id`
```