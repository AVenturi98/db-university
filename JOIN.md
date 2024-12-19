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