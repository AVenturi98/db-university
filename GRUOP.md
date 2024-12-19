<!-- 1. Contare quanti iscritti ci sono stati ogni anno -->

SELECT COUNT(*), YEAR(`enrolment_date`) AS `date`
FROM `students` 
GROUP BY `date`