## Desafio de projeto da DIO [Dashboard de Vendas com Power BI utilizando Star Schema](https://web.dio.me/lab/criando-um-star-schema-para-cenarios-de-vendas-com-power-bi/learning/cc70d8ef-2b44-4f53-a05b-643de8e5086b)

---

Para construir o esquema estrela (star schema) com base no diagrama relacional fornecido e focado na análise dos professores, foram seguidos os seguintes passos:

1. Identificação da Tabela Fato
A tabela fato conterá os dados principais relacionados ao professor e ao contexto da análise, que envolve os cursos ministrados, disciplinas, departamento, e informações de datas. Cada linha na tabela fato será uma instância de um professor ensinando um curso em um determinado departamento, com medidas como quantidade de disciplinas ou cursos ministrados.

2. Definição das Tabelas
As tabelas fornecerão contexto e detalhes adicionais às informações da tabela fato:

Professor: Detalhes sobre o professor, como nome, ID do professor, e status de coordenador.
Curso: Contém informações sobre os cursos ministrados pelos professores (ID, nome do curso, etc.).
Disciplina: Detalhes sobre as disciplinas ministradas pelo professor (ID, nome da disciplina, etc.).
Departamento: Detalhes sobre o departamento ao qual o professor pertence (ID, nome do departamento, campus, etc.).
Data: Representa as datas relevantes como data de início do curso, data de início da disciplina, etc.

3. Tabela Fato (Fato_Professor)
A tabela fato pode incluir medidas e chaves para se conectar com as tabelas. As colunas da tabela fato incluem:

idProfessor: Chave estrangeira para Professor.
idCurso: Chave estrangeira para Curso.
idDisciplina: Chave estrangeira para Disciplina.
idDepartamento: Chave estrangeira para Departamento.
idData: Chave estrangeira para Data.
Qtd_Disciplinas: Número de disciplinas ministradas.

4. Inclusão da Dimensão de Datas
A dimensão de datas conterá colunas como:

Data Completa (ex: '2024-10-01').
Ano, Mês, Dia.


Modelo Star Schema
Fato_Professor

idProfessor (FK)
idCurso (FK)
idDisciplina (FK)
idDepartamento (FK)
idData (FK)
Qtd_Disciplinas

Professor

idProfessor
idDepartameto
NomeProfessor
Coordenador

Curso

idCurso
NomeCurso

Disciplina

idDisciplina
idProfessor
NomeDisciplina

Departamento

idDepartamento
NomeDepartamento
Campus

Data

idData
Data
Ano
Mês
Dia


Passo a Passo no Power BI

1. Abrir o Power BI Desktop

2. Criar Tabelas Manualmente no Power BI
Como não temos os dados em arquivos externos, precisou criar as tabelas baseando-se nas entidades e atributos exibidos no diagrama.

Para visualizar as fórmulas DAX basta ir em exibição de modelo no arquivo Star-Schema e clicar no item.

3. Com as tabelas criadas é só cliar relacionamento entre as chaves estrangeira da tabela Fato_Professor e as chaves em suas respectivas tabelas.

Cosiderações:
Optou-se por gerar as tabelas no próprio PowerBI por simplificar o processo.
