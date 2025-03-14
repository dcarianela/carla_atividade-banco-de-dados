# Etapa 4 (FINAL)

## CRUD

1) Faça uma consulta que mostre os alunos que nasceram antes do ano 2009
```sql
SELECT nome, data_nascimento FROM alunos
WHERE data_nascimento < '2009-01-01';
```

2) Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.
```sql
SELECT nome, ROUND((primeira_nota + segunda_nota) / 2.0, 2) AS "Média das Notas"
FROM alunos;
```

3) Faça uma consulta que calcule o limite de faltas de cada curso de acordo com a carga horária. Considere o limite como 25% da carga horária. Classifique em ordem crescente pelo título do curso.
```sql
SELECT titulo, carga_horaria * 0.25 AS "Limite de Faltas" FROM cursos
ORDER BY titulo;
```

4) Faça uma consulta que mostre os nomes dos professores que são somente da área "desenvolvimento".
```sql
SELECT nome FROM professores
WHERE area_atuacao = 'desenvolvimento';
```

5) Faça uma consulta que mostre a quantidade de professores que cada área ("design", "infra", "desenvolvimento") possui.
```sql
SELECT area_atuacao, COUNT(id) AS "Quantidade de Professores" FROM professores
GROUP BY area_atuacao;
```

6) Faça uma consulta que mostre o nome dos alunos, o título e a carga horária dos cursos que fazem.
```sql
SELECT
    alunos.nome AS Nome,
    cursos.titulo AS Curso,
    cursos.carga_horaria AS "Carga Horária"
FROM alunos JOIN cursos
ON alunos.curso_id = cursos.id;
```

7) Faça uma consulta que mostre o nome dos professores e o título do curso que lecionam. Classifique pelo nome do professor.
```sql
SELECT
    professores.nome AS Professor,
    cursos.titulo AS Cursos
FROM professores JOIN cursos
ON professores.curso_id = cursos.id
ORDER BY professor;
```

8) Faça uma consulta que mostre o nome dos alunos, o título dos cursos que fazem, e o professor de cada curso.
```sql
SELECT
    alunos.nome AS Aluno,
    cursos.titulo AS Curso,
    professores.nome AS Professor
FROM alunos JOIN cursos ON alunos.curso_id = cursos.id
JOIN professores ON cursos.professor_id = professores.id;
```

9) Faça uma consulta que mostre a quantidade de alunos que cada curso possui. Classifique os resultados em ordem descrecente de acordo com a quantidade de alunos.
```sql
SELECT
    COUNT(alunos.id) AS Alunos,
    cursos.titulo AS Cursos
FROM alunos JOIN cursos ON alunos.curso_id = cursos.id
GROUP BY cursos.titulo;
```

10) Faça uma consulta que mostre o nome dos alunos, suas notas, médias, e o título dos cursos que fazem. Devem ser considerados somente os alunos de Front-End e Back-End. Mostre os resultados classificados pelo nome do aluno.
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

11) Faça uma consulta que altere o nome do curso de Figma para Adobe XD e sua carga horária de 10 para 15.
```sql
UPDATE cursos SET titulo = 'Adobe XD', carga_horaria = 15
WHERE id = 4;
```

12) Faça uma consulta que exclua um aluno do curso de Redes de Computadores e um aluno do curso de UX/UI.
```sql
DELETE FROM alunos WHERE id IN (9, 2);
```

13) Faça uma consulta que mostre a lista de alunos atualizada e o título dos cursos que fazem, classificados pelo nome do aluno.
```sql
SELECT
    alunos.nome AS Alunos,
    cursos.titulo AS Cursos
FROM alunos JOIN cursos ON alunos.curso_id = cursos.id
ORDER BY alunos;
```

---

### 🔥 DESAFIOS 🔥

Criar uma consulta que calcule a idade do aluno
```sql
SELECT nome,
    TIMESTAMPDIFF(YEAR, data_nascimento, '2025-03-14') AS Idade
FROM alunos
GROUP BY nome;
-- TIMESTAMPDIFF: calcula a diferença entre as data (medida de calculo, primeira data, segunda data)
```

Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média maior ou igual a 7.
```sql
SELECT nome, ROUND((primeira_nota + segunda_nota) / 2.0, 2) AS media_notas 
FROM alunos
GROUP BY nome
HAVING media_notas >= 7; -- HAVING: usado para filtrar resultados
```

Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média menor que 7.
```sql
SELECT nome, ROUND((primeira_nota + segunda_nota) / 2.0, 2) AS media_notas 
FROM alunos
GROUP BY nome
HAVING media_notas < 7;
```

Criar uma consulta que mostre a quantidade de alunos com média maior ou igual a 7.
```sql
SELECT COUNT(*) AS Aprovados -- COUNT(*): utilizado para contar as linhas de toda a tabela, por isso o uso do * 
FROM alunos
WHERE (primeira_nota + segunda_nota) / 2 >= 7;
```