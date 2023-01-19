# modelagemBD
simulação de um novo sistema com modelagem de um banco de dados que vai armazenar seus cursos, turmas e alunos.


ESQUEMA CONCEITUAL
![photo_2023-01-19_14-45-31](https://user-images.githubusercontent.com/94478634/213533080-f4a29e56-687a-415b-946f-f0e3dd8d22f0.jpg)

ESQUEMA LOGICO
![photo_2023-01-19_15-14-50 (2)](https://user-images.githubusercontent.com/94478634/213533084-82d9a2d2-b48d-4ba2-9a0f-07a1cfafb294.jpg)




⇨ Existem outras entidades além dessas três?
Obviavmente que haverá a necessidade de mais entidades
para fazer os respectivos relacionamentos e consultas.Eu por exemplo
tive de utilizar 8 entidades.

⇨ Quais são os principais campos e tipos?
Tabela: Curso
Campos Principais:
	id int PK
	nome varchar(255),
	perido:int,
	datainicio: datetime
	duracao varchar(255)

Tabela: Matricula
Campos Principais:
	curso_id: int FK
	aluno_id: int FK
	situacao: varchar(255)
	datamatricula: datetime




Tabela: aluno
Campos Principais:
	id int PK
	nome:varchar(255)
	nascimento:datetime

Tabela: Disciplina
Campos Principais:
	id: int PK
	nome: varchar(255)
	semestre: int
	totalaulas:int


Tabela: aluno_disciplina
Campos Principais:
	aluno_id int FK
	disciplina_id int FK


Tabela: Turma
Campos Principais:
	id int PK
	codigo: varchar(255)


Tabela: aluno_turma
Campos Principais:
	id: int PK
	codigo: varchar(255)

Tabela: professor
CamposPrincipais:
	id int PK
	nome varchar(255)
	nascimento datetime
	salario varchar (255)


Tabela: professor turma
CamposPrincipais:
	turma_id int FK
	prof_id int  FK


⇨ Como essas entidades estão relacionadas?

Tabela curso([id]PK) haverá uma relação entre a tabela matricula([curso_id]FK)
Tabela aluno([id]PK) haverá uma relação entre a tabela matricula([aluno_id]FK)
Tabela Matricula([aluno_id]FK) chave estrangeira da tabela aluno([id]PK)
Tabela Matricula(curso_id]FK) chave estrangeira da tabela curso([id]PK)



Tabela Disciplina([id]PK) haverá uma relação entre a tabela turma([disciplina_id]FK)
Tabela Disciplina([id]PK) haverá uma relação entre a tabela aluno_disciplina([aluno_id]FK)
Tabela Aluno([id]PK) haverá uma relação entre a tabela aluno_disciplina([disciplina_id]FK)
Tabela aluno_disciplina([aluno_id]FK) chave estrangeira da tabela aluno([id]PK)
Tabela aluno_disciplina([_id]FK) chave estrangeira da tabela Disciplina([id]PK)


Tabela Turma([id]PK) haverá uma relação entre a tabela aluno_turma([turma_id]FK)
Tabela Aluno([id]PK) haverá uma relação entre a tabela aluno_turma([alunoturma_id]FK)
Tabela aluno_turma([turma_id]FK) chave estrangeira da tabela turma([id]PK)
Tabela aluno_turma([alunoturma_id]FK) chave estrangeira da tabela aluno([id]PK)



Tabela Turma([id]PK) haverá uma relação entre a tabela professor_turma([turma_id]FK)
Tabela Professor([id]PK) haverá uma relação entre a tabela professor_turma([prof_id]FK)
Tabela professor_turma([turma_id]FK) chave estrangeira da tabela turma([id]PK)
Tabela professor_turma([prof_id]FK) chave estrangeira da tabela turma([id]PK)









