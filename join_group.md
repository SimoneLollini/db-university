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
  
```
- Contare quanti corsi di laurea ci sono per ogni dipartimento
```sql
  
```

Join:
- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```sql
```
- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
```sql
```
- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```sql
```
- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico  per cognome e nome
- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
```sql

```
- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
```sql

```
- BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami
```sql

```