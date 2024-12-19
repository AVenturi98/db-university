<!-- 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia -->

SELECT *
FROM `students`
INNER JOIN `degrees` AS `d`
ON `d`.`id` = students.degree_id AND `d`.`name` LIKE 'Corso di Laurea in Economia'

