# Etapa 3

## Modelagem Física

```sql
CREATE DATABASE tecinternet_escola_carla CHARACTER SET utf8mb4;

CREATE TABLE cursos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(100) NOT NULL,
    carga_horaria INT NOT NULL
    professor_id INT NULL
)

CREATE TABLE professores(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(150) NOT NULL,
    area_atuacao ENUM('infra', 'design', 'desenvolvimento') NOT NULL,
    curso_id INT NOT NULL
)

CREATE TABLE alunos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(150) NOT NULL,
    data_nascimento DATE NOT NULL,
    primeira_nota DECIMAL(5,2) NOT NULL,
    segunda_nota DECIMAL(5,2) NOT NULL,
    curso_id INT NOT NULL
)
```



