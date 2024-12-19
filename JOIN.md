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