<!-- 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia -->

SELECT *
FROM `students`
INNER JOIN `degrees` AS `d`
ON `d`.`id` = students.degree_id AND `d`.`name` LIKE 'Corso di Laurea in Economia'

<!--  2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze -->

SELECT *
FROM `departments` AS `dep`
INNER JOIN `degrees` AS `dg`
ON `dg`.`department_id` = `dep`.`id` AND `dep`.`name` LIKE '%Neuroscienze'

<!-- 3. Selezionar tutti i corsi in cui insegnava fulvio Amato (id = 44) -->

SELECT *
FROM `course_teacher` AS `c_t` 
INNER JOIN `teachers` AS `t`
ON `t`.`id` = `c_t`.`teacher_id` AND `id` LIKE 44

<!-- 4. Selezionare tutti gli studenti con i dati realativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in oridine alfabetico per cognome e nome -->

SELECT *
FROM `students`
JOIN `degrees` AS `d`
ON `students`.`degree_id` = `d`.`id` 
JOIN `departments` 
ON `d`.`department_id` = `departments`.`id` 

<!-- 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti -->

SELECT *
FROM `courses` AS `c`
JOIN `degrees` AS `d`
ON `c`.`degree_id` = `d`.`id` 
JOIN `teachers` AS `t` 
ON `d`.`id` = `t`.`id` 

<!-- 6. Selezionare titto i docenti che insegnano nel Dipartimento di Matematica -->

FROM `courses` AS `c`
JOIN `degrees` AS `d`
ON `c`.`degree_id` = `d`.`id` 
JOIN `teachers` AS `t` 
ON `d`.`id` = `t`.`id` 
JOIN `departments` AS `dep`
ON `dep`.`id` = `d`.`id`
WHERE `dep`.`name` LIKE '% Matematica' AND `dep`.`id` = `t`.`id`
