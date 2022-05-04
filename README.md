# SQL
Code sql example to use

CREATE DATABASE es21;

USE es21;

CREATE TABLE departamento (
    dep_codigo INT PRIMARY KEY,
    dep_nome VARCHAR(85) NOT NULL
);

CREATE TABLE curso (
    cur_codigo INT PRIMARY KEY,
    cur_nome VARCHAR(85) NOT NULL,
    dep_codigo INT NOT NULL,
    CONSTRAINT fk_curso_departamento FOREIGN KEY (dep_codigo) 
        REFERENCES departamento (dep_codigo)
)
'Inserir em departamento'

INSERT INTO departamento (dep_codigo, dep_nome)
    VALUES(1, 'Departamento Acadêmico de Mecânica');

SELECT * fROM es21.departamento;

'Inserir em curso'

INSERT INTO curso
    VALUES(1, 'Engenharia de Software', 1);

SELECT * FROM es21.curso;

'Update em todas as bolsas de estudo dos alunos'
UPDATE aluno
    SET alu_vlr_bolsa = alu_vlr_bolsa * 1.05;

'Update em alunos que não nasceram em cp'
UPDATE aluno    
    SET alu_vlr_bolsa = alu_vlr_bolsa * 1.02
        WHERE cid_codigo <> 1;
                        '!='   
'Update apelido para engenheiros mecanicos que ganham mais de R$500'
UPDATE aluno    
    SET alu_apelido = 'Ganha demais'
        WHERE alu_vlr_bolsa > 500 AND cur_codigo = 1;

'Delete os alunos cujo valor < 500'
DELETE FROM aluno;
    WHERE alu_vlr_bolsa < 500;


