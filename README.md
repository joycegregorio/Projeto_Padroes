Requisitos do Sistema
Requisitos Funcionais
- O sistema deve permitir o cadastro de professores.
- Professores cadastrados devem conseguir fazer login no sistema.
- Professores devem poder visualizar os horários disponíveis e ocupados de cada laboratório.
- O professor pode editar suas disciplinas.
- Professores podem reservar horários para uso do laboratório.
- O sistema deve permitir cancelar reservas.
- Deve haver a persistência de dados para garantir que as informações de login e agendamentos sejam salvas.
- Professores devem conseguir ver os horários reservados por outros professores e não poderá alterá-los.
Requisitos Não Funcionais
- O sistema deve ser amigável e de fácil uso, utilizando uma interface gráfica simples e intuitiva.
- As informações de login e agendamento devem ser armazenadas de forma segura, utilizando persistência de dados.
- O sistema deve garantir que não haja conflitos de horários entre os professores.
- Deve ser garantida a responsividade e eficiência na interação com o usuário, sem atrasos significativos.
Estrutura do Sistema
A estrutura do sistema é criada no pacote “ifpb.edu.br.main”, a partir desse pacote, todas as classes de controller, view, dao e model são devidamente separadas.
No package controller estão contidas as classes controlador e dados. 
- Classe controlador: Conta com chamadas de classes do sistema, como “Dados”, “Serializador”, “Controlador”, “Professor”, “BlocoDeHorario”, “CalendarioSemanal” e “InfoBloco”.
Essas classes representam os dados onde serão armazenados e criados e estão sendo chamadas na classe controlador para que a mesma consiga controlar os métodos de funcionamento dos dados das classes. 
- Classe dados: Conta com a incialização das listas de professor e disciplina para atualizar-las a cada novo dado adicionado no sistema.
No package view estão contidas as classes BlocoDeHorario, BotaoAlocacao, CalendarioSemanal, GerenciadorDeTelas, InfoBlocos, JanelaCalendario, TelaCadastro, TelaLogin e TelaPrincipal.
- Classe BlocoDeHorario: Conta com a incialização da matriz contendo os blocos de horário e a chamada da classe "InfoBlocos", para que as informações necessárias estejam dentro dos blocos criados na classe.
- Classe BotaoAlocacao: Conta com dois atributos strings, disciplina e professor, para que essas sejam as informações presentes dentro do blocoDeHorario quando o horário for reservado por determinado professor.
- Classe CalendarioSemanal: Conta com a lista de BlocoDeHorario e o int semanaAtual, iniciando de fato os blocos de horário dentro de um for e métodos para que esses hórarios sejam atualizados conforme as semanas e meses, como por exemplo o método "atualizarMes".
- Classe GerenciadorDeTelas: Onde fica todo o gerenciamento de visualização de telas, onde organiza toda a ordem de aparição das telas e suas devidas validações para avançar de uma para a outra.
- Classe InfoBlocos: Conta com a criação das matrizes de disciplina e professor e sua alocação no bloco, se está ocupado ou não.
- Classe JanelaCalendario: Onde é organizado todo o componente de agendamento utilizando as classes de "InfoBloco", "BlocoDeHorario", "CalendarioSemanal" e "BotaoAlocacao". 
- Classe TelaCadastro: Conta com os métodos e chamadas de classes necessárias para a criação da tela de cadastro, para cadastrar e salvar os dados de cada professor que desejar se cadastrar no sistema.
- Classe TelaLogin: Conta com os métodos e chamadas de classes necessárias para a criação da tela de login, para entrar no sistema pegando os dados de cada professor que se cadastrou no sistema.
- Classe TelaPrincipal: Tela principal armazena as chamadas da classes "Controlador", "CalendarioSemanal" e "JanelaCalendario", alocando as três classes dentro de um painel.
No package dao estão contidas as classes Disciplina, DisciplinaDAOImpl, Professor, ProfessorDAOImpl, Serializador e StringSerializer.
- Nesse pacote é onde acontece toda a serialização dos dados de disciplina e professor e suas devidas implementações de envio de dados e leitura dos mesmos.
No package model estão contidas as classes Disciplina, Professor e Laboratorio.
- Classe Disciplina: Estão contidos os atributos de disciplinas, como nomeDisciplina e a chamada da classe Professor, juntamente com os gets e sets.
- Classe Professor: Estão contidos os atributos de professor, como nome, matricula, senha e uma lista das disciplinas que são ministradas por esse professor, juntamente com os gets e sets.
- Classe Laboratorio: Estão contidos um id de cada laboratório que está alocado nos blocos de horário e a chamada de uma lista de BlocosDeHorarios para serem feitos os agendamentos de horário.

