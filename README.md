<!-- 1. Selezionare tutti gli studenti nati nel 1990 (160) --> 

SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990

<!-- 2. Selezionare tutti i corsi che valgono più di 10 crediti (479) -->

SELECT *
FROM `courses`
WHERE `cfu` > 10

<!-- 3. Selezionare tutti gli studenti che hanno più di 30 anni -->

SELECT *
FROM `students` 
WHERE `date_of_birth` < DATE_SUB(CURDATE(), INTERVAL 30 YEAR) <!-- (3788) -->

<!-- 4. Selezionare tutti i corsi del primo semestre di un qualsiasi corso di laurea (286)-->

SELECT * 
FROM `courses`
WHERE `year` LIKE 1 AND `period` LIKE 'I semestre' <!-- (10) -->

SELECT COUNT(id)
FROM `COURSES` 
WHERE period LIKE 'I semestre' <!-- 709 -->

<!-- 5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21) -->

SELECT *
FROM `exams` 
WHERE `hour` >= '14:00:00' AND `date` = '2020-06-20'

<!-- 6. Seleziona tutti i corsi di laurea magistrale (38) -->

SELECT *
FROM `degrees` 
WHERE `level` LIKE 'magistrale'

<!-- 7. Da quanti compartimenti è composta l'università? (12) -->

SELECT COUNT(id)
FROM `departments` 

<!-- 8.Quanti sono gli insegnanti che non hanno un numero di telefono? (50) -->

SELECT COUNT(id)
FROM `teachers` 
WHERE `phone` IS NULL

<!-- 9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale) -->

SELECT *, CONCAT(name, ' ', surname, ' | ', 'degreeID: ',degree_id, ' | ', email) AS data_user
FROM `students`

  <!------------------------------------->

INSERT INTO `students` (degree_id, name, surname, date_of_birth, fiscal_code, enrolment_date, registration_number, email)
VALUES (73, 'Alessandro', 'Venturi', '1998-10-10', 'ABCDEFGHILMNOPQR', CURDATE(), FLOOR(RAND(999999)), 'tantisalutid@santolussurgiu.com');

<!-- 10. Cambiare in numero dell'ufficio del professor Pietro Rizzo in 216 -->

UPDATE `teachers`
SET office_number = 126
WHERE id = 58

<!-- 11. Eliminare dalla tabella studenti il record creato precedentemente a punto 9 -->

DELETE FROM `students` WHERE id = 5012