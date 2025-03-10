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