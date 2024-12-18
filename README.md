# DB-UNIVERSITY

### 1. Selezionare tutti gli studenti nati nel 1990 (160)
``` sql
SELECT *
FROM `students`
WHERE YEAR(date_of_birth) = 1990;
```

### 2. Selezionare tutti i corsi che valgono più di 10 crediti (479)
``` sql
SELECT *
FROM `courses`
WHERE `cfu` > 10;
```

### 3. Selezionare tutti gli studenti che hanno più di 30 anni
``` sql
SELECT *
FROM `students`
WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) >= 30;
```

### 4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
``` sql
SELECT *
FROM `courses`
WHERE `period` = 'I semestre' AND `year` = 1;
```