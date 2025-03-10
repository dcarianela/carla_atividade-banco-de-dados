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