# Etapa 4 (FINAL)

## CRUD

```sql
SELECT nome, data_nascimento FROM alunos
WHERE data_nascimento < '2009-01-01';
```
```

```sql
SELECT titulo, carga_horaria * 0.25 AS "Limite de Faltas" FROM cursos
ORDER BY titulo;
```

```sql
SELECT nome FROM professores
WHERE area_atuacao = 'desenvolvimento';
```

```sql
SELECT area_atuacao, COUNT(id) AS "Quantidade de Professores" FROM professores
GROUP BY area_atuacao;
```

```sql
SELECT
    alunos.nome AS Nome,
    cursos.titulo AS Curso,
    cursos.carga_horaria AS "Carga Horária"
FROM alunos JOIN cursos
ON alunos.curso_id = cursos.id;
```

```sql
SELECT
    professores.nome AS Professor,
    cursos.titulo AS Cursos
FROM professores JOIN cursos
ON professores.curso_id = cursos.id
ORDER BY professor;
```

```sql
SELECT
    alunos.nome AS Aluno,
    cursos.titulo AS Curso,
    professores.nome AS Professor
FROM alunos JOIN cursos ON alunos.curso_id = cursos.id
JOIN professores ON cursos.professor_id = professores.id;
```

```sql
SELECT
    COUNT(alunos.id) AS Alunos,
    cursos.titulo AS Cursos
FROM alunos JOIN cursos ON alunos.curso_id = cursos.id
GROUP BY cursos.titulo;
```

```sql
SELECT
    alunos.nome AS Alunos,
    alunos.primeira_nota AS "Nota 1",
    alunos.segunda_nota AS "Nota 2",
    ROUND((alunos.primeira_nota + alunos.segunda_nota) / 2.0, 2) AS "Média das Notas",
    cursos.titulo AS Cursos
FROM alunos JOIN cursos ON alunos.curso_id = cursos.id
WHERE cursos.titulo IN ('Front-End', 'Back-End')
ORDER BY alunos;
```

```sql
UPDATE cursos SET titulo = 'Adobe XD', carga_horaria = 15
WHERE id = 4;
```

```sql
DELETE FROM alunos WHERE id IN (9, 2);
```

```sql
SELECT
    alunos.nome AS Alunos,
    cursos.titulo AS Cursos
FROM alunos JOIN cursos ON alunos.curso_id = cursos.id
ORDER BY alunos;
```

