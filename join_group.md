Group by:
- Contare quanti iscritti ci sono stati ogni anno
```sql
    SELECT year(`students`.`enrolment_date`) AS `year`, 
    COUNT(`students`.`id`)
    FROM `students` 
    GROUP BY `students`.`enrolment_date`;
```

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```sql
    SELECT `teachers`.`office_address`, 
    COUNT(`teachers`.`id`) AS `teachers` 
    FROM `teachers`
    GROUP BY `teachers`.`office_address`;
```


- Calcolare la media dei voti di ogni appello d'esame
```sql
    SELECT `exam_student`.`exam_id`,
    AVG(`exam_student`.`vote`) AS `average` 
    FROM `exam_student` 
    GROUP BY `exam_student`.`exam_id`;
```
- Contare quanti corsi di laurea ci sono per ogni dipartimento
```sql
    SELECT `department_id` AS 'n_departments',
    COUNT(`id`) AS 'n_course_degree'
    FROM `degrees` 
    GROUP BY `department_id`;
```

Join:
- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```sql
    SELECT `students`.*,
    `degrees`.`name` from `students` 
    JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` 
    WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```
- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
```sql
    SELECT `degrees`.*,
    `departments`.`name`
    FROM `degrees` 
    JOIN `departments` 
    ON `departments`.`id` = `degrees`.`department_id` 
    WHERE `departments`.`name` = 'Dipartimento di Neuroscienze' AND `degrees`.`level` = 'magistrale';
```
- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```sql
    SELECT `courses`.* , `teachers`.`name`, `teachers`.`surname` FROM `course_teacher` JOIN `courses` ON    `courses`.`id` = `course_teacher`.`course_id` JOIN `teachers` ON `teachers`.`id` = `course_teacher`.   `teacher_id` WHERE `teachers`.`id` = 44;
```
- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico  per cognome e nome
```sql
    SELECT `students`.`name` AS 'students_name',`students`.`surname` AS 'students_surname', `degrees`.* , `departments`.`name` AS 'departments_name' 
    FROM `degrees` 
    JOIN `students` on `degrees`.`id` = `students`.`degree_id` 
    JOIN `departments` ON `degrees`.`department_id` = `departments`.`id` 
    ORDER BY `students`.`surname` ASC, `students`.`name` ASC;
```
- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
```sql
    SELECT `students`.`name` AS 'students_name',`students`.`surname` AS 'student_surname', `degrees`.* , `departments`.`name` AS 'departments_name' 
    FROM `degrees` 
    JOIN `students` ON `degrees`.`id` = `students`.`degree_id` 
    JOIN `departments` ON `degrees`.`department_id` = `departments`.`id` 
    ORDER BY `students`.`surname` ASC, 
    `students`.`name` ASC;
```

- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
```sql

```
- BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami
```sql

```