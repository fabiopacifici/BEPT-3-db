# University

~~Modellare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi `Dipartimenti` (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni `Dipartimento` offre più `Corsi di Laurea` (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni `Corso di Laurea` prevede diversi `Corsi` (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni `Corso` può essere tenuto da diversi `Insegnanti`;
ogni `Corso` prevede più appelli d'`Esame`;
ogni `Studente` è iscritto ad un solo `Corso di Laurea`;~~
ogni `Studente` può iscriversi a più appelli di `Esame`;
per ogni appello d'`Esame` a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.

## Table: departments

- id BIGINT PK AI NOTNULL UNIQUE

## Table: degrees

- id BIGINT PK AI NOTNULL UNIQUE
- department_id UNSIGNED BIGINT FK

## Table: courses

- id BIGINT PK AI NOTNULL UNIQUE
- degree_id UNSIGNED BIGINT FK

## Table: teachers

- id BIGINT PK AI NOTNULL UNIQUE

## Table (pivot) course_teacher

- id BIGINT PK AI NOTNULL UNIQUE
- course_id UNSIGNED BIGINT FK
- teacher_id UNSIGNED BIGINT FK

## Table: exams

- id BIGINT PK AI NOTNULL UNIQUE
- course_id UNSIGNED BIGINT FK

## Table: students

- id BIGINT PK AI NOTNULL UNIQUE
- degree_id UNSIGNED BIGINT FK

## Table (pivot): exam_student

- id BIGINT PK AI NOTNULL UNIQUE
- exam_id
- student_id
- vote
