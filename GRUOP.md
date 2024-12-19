<!-- 1. Contare quanti iscritti ci sono stati ogni anno -->

SELECT COUNT(*), YEAR(`enrolment_date`) AS `date`
FROM `students` 
GROUP BY `date`

<!-- 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio -->

SELECT COUNT(*), `office_address`
FROM `teachers` 
GROUP BY `office_address`

<!-- 3. Calcora la media dei voti di ogni appello d'esame -->

SELECT COUNT(`exam_id`) AS 'exam', FLOOR(AVG(`vote`)) AS 'vote_average'
FROM `exam_student` 
GROUP BY `vote`
