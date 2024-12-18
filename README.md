<!-- 1. Selezionare tutti gli studenti nati nel 1990 (160) --> 

SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990

<!-- 2. Selezionare tutti i corsi che valgono più di 10 crediti (479) -->

SELECT *
FROM `courses`
WHERE `cfu` = 10

<!-- 3. Selezionare tutti gli studenti che hanno più di 30 anni -->

SELECT * 
FROM `students`
WHERE YEAR(date_of_birth) < 1993  <!-- (3501) -->

<!-- 4. Selezionare tutti i corsi del primo semestre di un qualsiasi corso di laurea (286)-->

SELECT * 
FROM `courses`
WHERE degree_id LIKE 1 AND period LIKE 'I semestre' <!-- (10) -->