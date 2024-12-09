Scripts PL/SQL para Gerenciamento de Alunos, Disciplinas e Professores

Descrição
Este projeto contém scripts PL/SQL para gerenciar entidades de Alunos, Disciplinas e Professores em um banco de dados Oracle. O conjunto de pacotes implementa operações de exclusão, listagem, cadastro e cálculos relacionados às entidades.

Execução
1. Configuração do ambiente:
   - Certifique-se de que o Oracle Database está instalado e em execução.
   - Use uma ferramenta como Live SQL (online), SQL Developer ou outra de sua preferência para se conectar ao banco de dados Oracle.

2. Execução do script:
   - Abra a ferramenta de sua escolha e conecte-se ao banco de dados Oracle.
   - Copie e cole o conteúdo do arquivo `codigo.sql` na janela de comando da ferramenta.
   - Execute o script para criar as tabelas, sequências e pacotes.


Conteúdo do Script

Criação das tabelas e sequências:
O script cria as sequências e tabelas necessárias para gerenciar as entidades de Alunos, Professores, Cursos, Disciplinas, Matrículas e Turmas.


Pacotes:

PKG_ALUNO
- ExcluirAluno(p_id_aluno IN NUMBER): Exclui um aluno pelo ID, removendo também todas as matrículas associadas.
- ListarAlunosMaiores18: Lista o nome e a data de nascimento de todos os alunos com mais de 18 anos.
- ListarAlunosPorCurso(p_id_curso IN NUMBER): Lista os nomes dos alunos matriculados em um curso específico.

PKG_DISCIPLINA

- CadastrarDisciplina(p_nome IN VARCHAR2, p_descricao IN CLOB, p_id_curso IN NUMBER, p_carga_horaria IN NUMBER): Cadastra uma nova disciplina.
- TotalAlunosPorDisciplina: Exibe o número total de alunos matriculados em cada disciplina que tem mais de 10 alunos.
- MediaIdadePorDisciplina(p_id_disciplina IN NUMBER): Calcula a média de idade dos alunos matriculados em uma disciplina específica.
- ListarAlunosDisciplina(p_id_disciplina IN NUMBER): Lista os nomes dos alunos matriculados em uma disciplina específica.

PKG_PROFESSOR

- TotalTurmasPorProfessor: Lista os nomes dos professores e o total de turmas que cada um leciona, mostrando apenas os professores responsáveis por mais de uma turma.
- TotalTurmasDeProfessor(p_id_professor IN NUMBER) RETURN NUMBER: Retorna o total de turmas em que um professor específico atua como responsável.
- ProfessorDeDisciplina(p_id_disciplina IN NUMBER) RETURN VARCHAR2: Retorna o nome do professor que ministra uma disciplina específica.