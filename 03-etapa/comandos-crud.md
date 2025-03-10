# Etapa 3

## CRUD

```sql
INSERT INTO cursos (titulo, carga_horaria) VALUES(
    'Front-End',
    40
),
(   'Back-End',
    80
),
(   'UX/UI Design',
    30
),
(   'Figma',
    10
),
(   'Redes de Computadores',
    100
);

INSERT INTO professores (nome, area_atuacao, curso_id) VALUES(
    'Jon Oliva',
    'infra',
    5
),
(
    'Lemmy Kilmister',
    'design',
    4
),
(
    'Neil Peart',
    'design',
    3
),
(
    'Ozzy Osbourne',
    'desenvolvimento',
    2
),
(
    'David Gilmour',
    'desenvolvimento',
    1
);
```

---

```sql
UPDATE cursos SET professor_id = 1
WHERE id = 5;

UPDATE cursos SET professor_id = 2
WHERE id = 4;

UPDATE cursos SET professor_id = 3
WHERE id = 3;

UPDATE cursos SET professor_id = 4
WHERE id = 2;

UPDATE cursos SET professor_id = 5
WHERE id = 1;
```

---

```sql
INSERT INTO alunos (nome, data_nascimento, curso_id, primeira_nota, segunda_nota) VALUES(
    'Osamu Dazai',
    '1909-06-19',
    5,
    3.0,
    5.0
),
(   'Chihiro Ogino',
    '1990-05-25',
    3,
    9.0,
    8.5
),
(   'Shinji Ikari',
    '1985-06-06',
    1,
    6.5,
    7.5
),
(   'Lelouch Lamperouge',
    '2000-12-05',
    4,
    8.0,
    9.5
),
(   'Mikasa Ackerman',
    '1995-02-10',
    2,
    7.0,
    8.0
),
(   'Light Yagami',
    '1986-02-28',
    2,
    9.5,
    9.0
),
(   'Eren Yeager',
    '1996-07-30',
    4,
    6.0,
    7.0
),
(   'Natsu Dragneel',
    '1993-03-02',
    1,
    8.5,
    3.5
),
(   'Saber',
    '1990-01-11',
    5,
    7.5,
    8.0
),
(   'Kagome Higurashi',
    '1993-04-15',
    3,
    3.0,
    6.5
);

```