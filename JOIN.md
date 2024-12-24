# JOIN

### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
``` sql
SELECT *
FROM `students`
JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia'
```

### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
``` sql
SELECT DISTINCT `degrees`.`name` AS course_name, `degrees`.`level` AS course_level
FROM `degrees`
JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze' AND `degrees`.`level` = 'Magistrale'
```

### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
``` sql
SELECT c.`name` AS course_name
FROM `courses` AS c
JOIN `course_teacher` AS ct 
ON c.`id` = ct.`course_id`
JOIN `teachers` AS t 
ON ct.`teacher_id` = t.`id`
WHERE t.`id` = 44;
```

### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
``` sql
SELECT `s`.*, `d`.`name` AS `degree_name`, `dep`.`name` AS `department_name`
FROM `departments` AS `dep`
JOIN `degrees` AS `d`
ON `d`.`department_id` = `dep`.`id`
JOIN `students` AS `s`
ON `s`.`degree_id` = `d`.`id`
ORDER BY `s`.`surname`, `s`.`name` ASC
```

### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
``` sql
SELECT *
FROM `degrees`
JOIN `courses`
ON `courses`.`degree_id` = `degrees`.`id`
JOIN `course_teacher`
ON `course_teacher`.`course_id` = `course_id`
JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`
```

### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
``` sql
SELECT `t`.*
FROM `departments` AS `dep`
JOIN `degrees` AS `d`
ON `dep`.`id` = `d`.`department_id`
JOIN `courses` AS `c`
ON `c`.`degree_id` = `d`.`id`
JOIN `course_teacher` AS `c_t`
ON `c_t`.`course_id` = `c`.`id`
JOIN `teachers` AS `t`
ON `c_t`.`teacher_id` = `t`.`id`
WHERE `dep`.`name` = 'Dipartimento di Matematica'
```