# Relatório de Encerramento

## Histórico de versões

| Versão | Data       | Descrição             | Autores     |
| ------ | ---------- | --------------------- | ----------- |
| 1.0    | 11/09/2024 | Abertura do documento | [Sebastián Zuzunaga](https://github.com/sebazac332) |
| 1.1    | 12/09/2024 | Adição de US executadas | [Sebastián Zuzunaga](https://github.com/sebazac332) |
| 1.2    | 19/09/2024 | Melhora organização do documento | [Amanda Nobre](https://github.com/AmandaNbr) |
| 1.3    | 22/09/2024 | Adição de informações | [Amanda Nobre](https://github.com/AmandaNbr) |

## Introdução

Este documento de encerramento apresentará uma análise comparativa entre o que foi planejado pela equipe e o que foi realizado durante o desenvolvimento do projeto. Serão abordados aspectos como backlog, custo, qualidade e riscos. Essa análise tem o objetivo de ilustrar a visão inicial da equipe em contraste com os resultados alcançados, além de servir como um guia para futuros desenvolvedores, oferecendo insights sobre o planejamento e a execução da solução proposta.

## Backlog

### Backlog Deprecado

Como citado no [Post Mortem](https://fga-eps-mds.github.io/2024-1-GEROcuidado-Doc/encerramento/post_mortem/), houve uma troca de contexto ao longo do projeto, dessa forma esta versão do backlog acabou sendo deprecada, porém a título de documentar e informar o que foi planejado inicialmente estarão descritas as US`s planejadas, executadas e aceitas.

#### Planejado

- **MVP**
	- [US01] Criar perfil de usuário
	- [US02] Editar informações pessoais
	- [US03] Cadastrar, visualizar, editar e apagar perfis de idosos
	- [US04] Cadastrar medicamentos e alimentos no perfil do idoso
	- [US05] Cadastrar, visualizar, editar e apagar tarefas da rotina do idoso
	- [US06] Cadastrar, visualizar, editar e apagar métricas de um idoso

- **Incremento**
	- [US07] Criar, visualizar, editar e apagar postagens no fórum
	- [US08] Tutorial explicativo das funcionalidades do aplicativo
	- [US09] Moderção das publicações do fórum

#### Executado
- [US01] Criar perfil de usuário
- [US04] Cadastrar medicamentos e alimentos no perfil do idoso

#### Aceito pelo Cliente
- [US01] Criar perfil de usuário
- [US04] Cadastrar medicamentos e alimentos no perfil do idoso

### Backlog Novo

Foi necessária a criação de um novo backlog para contemplar o novo cenário em que o projeto se encontrava, este descreve a situação atual do projeto. Dessa forma as US`s desta versão dizem respeito a melhorias (EH) e ajuste de bugs (BUG):

#### Planejado

- **MVP**
	- [EH01] Editar informações do perfil de usuário offline
	- [EH02] Cadastrar medicamentos e alimentos no perfil do idoso
	- [EH03] Cadastrar, visualizar, editar e apagar perfis de idosos offline
	- [EH04] Cadastrar, visualizar, editar e apagar métricas de um idoso
	- [EH05] Cadastrar, visualizar, editar e apagar tarefas da rotina do idoso
	- [BUG01] Resolver bugs de experiencia de usuário

#### Executado
- [EH01] Editar informações do perfil de usuário offline
- [EH03] Cadastrar, visualizar, editar e apagar perfis de idosos offline
- [EH04] Cadastrar, visualizar, editar e apagar métricas de um idoso
- [EH05] Cadastrar, visualizar, editar e apagar tarefas da rotina do idoso
- [BUG01] Resolver bugs de experiencia de usuário

#### Aceito pelo Cliente
- Nenhuma

### Situação atual do projeto

Dessa forma, as funcionalidades que estão presentes na versão atual do app são as contempladas no [relatório de encerramento](https://fga-eps-mds.github.io/2023-2-GEROcuidado-Doc/encerramento/relatorio_encerramento/) da equipe do semestre anterior (2023.2):

![image](https://github.com/user-attachments/assets/5df47cd6-71c6-4d82-8460-0cc7f5fd25f5)

Juntamente com as melhorias feitas no semestre atual deste projeto (2024.1), que fazem as funcionalidades que vieram do projeto de 2023.2 (*menos a interação com o fórum*) passarem a funcionar tanto com conexão a internet, quanto sem conexão. 
Esse requisito surgiu após conversar com o cliente e perceber que houveram dificuldades na homologação do app em casas de repouso que não tinham internet boa e/ou sinal para 3g/4g.


#### Funcionalidades

No projeto, as funcionalidades presentes podem ter três características:

1. Ser Offline
2. Ser Apenas Online
3. Ter Sincronização

- Ser Offline

Uma funcionalidade ser Offline, significa que a mesma funciona no dispositivo do usuário mesmo sem conexão com a Internet. Isto é, o usuário é capaz de utiliza-la em sua totalidade estando offline.

- Ser Apenas Online

Uma funcionalidade ser apenas Online, significa que a funciona no dispositivo do usuário apenas quando há internet. Uma vez interrompida a conexão, o usuário não será mais capaz de interagir com aquela parte do sistema.

- Ter Sincronização

Uma funcionalidade possuir sincronização significa que os dados que são persistidos no dispositivo do usuário, são enviados para a nuvem, isto é, para os micro-serviços.

No semestre anterior o aplicativo funcionava apenas online. Então, o banco de dados que persistia o que o usuário cadastrava ficava na "nuvem". Com a introdução da possibilidade da funcionalidade ser offline, surgiu também essa necessidade de sincronizar.

:warning: **Observação:** A sincronização nesse ponto do projeto não traz nenhum benefício. Esse benefício só será observado quando houver compartilhamento de informações entre contas, ou portabilidade de contas entre aparelhos. 

#### _As is_ do projeto

Abaixo está a relação de funcionalidades do aplicativo e seus meios de funcionamento.

| Funcionalidade | Online e Offline | Apenas Online | Sincronização | 
|:--------------:| :-----: | :-----------: | :-----------: |
| Login          |         |      X        | X |
| CRUD de Idoso    |    X    | | |
| CRUD de Rotina (tarefa) | X | | |
| CRUD de Métricas | X | | |
| Forum | | X | |

## Custo

<iframe src="https://docs.google.com/spreadsheets/d/1AfbnaR35DlNhQVRTdZQjuMkAz1KyYZplQHarhOnHLr0/pubhtml?widget=true&amp;headers=false"width="100%" width= "100" height="500" frameborder="1" scrolling="no"></iframe>

## Qualidade

Com o objetivo de manter a qualidade do código do trabalho, foram realizados diversos testes, cada um deles garantindo o correto funcionamento de um componente do trabalho. Atualmente o projeto tem uma cobertura de teste de mais de 80% no repositório do FrontEnd e mais de 90% nos repositórios dos serviços.

## Riscos

### Riscos planejados


| Risco | Descrição                                     |
|-------|-----------------------------------------------|
| R01   | Dificuldade com as tecnologias definidas      |
| R02   | Saída de algum integrante do projeto           |
| R03   | Falta de participação de algum integrante do projeto |
| R04   | Falta de integração da equipe                 |
| R05   | Divergência nos horários disponíveis dos integrantes |
| R06   | Alteração no escopo do projeto                |
| R07   | Integrante com problema de saúde             |
| R08   | Indisponibilidade do cliente                  |
| R09   | Falta de disponibilização de releases para o cliente testar |
| R10   | Falta de participação durante as reuniões     |
| R11   | Sobrecarga de membros da equipe               |
| R12   | Falha de equipamento                          |
| R13   | Dependência entre atividades                  |
| R14   | Problemas com a infraestrutura de rede        |
| R15   | Dificuldade na adaptação a novas ferramentas  |

### Acompanhamento dos riscos

<iframe width="700" height="760" src="https://docs.google.com/spreadsheets/d/111wcWXgaBPPJazR3fM-vaDZLNRwU9FPkP42Xga_8N6s/edit?usp=sharing"></iframe>

### Análise dos riscos
#### Riscos individuais

![image](https://github.com/user-attachments/assets/1a89db3a-90ec-446e-993a-ad0c927a09b1)

A partir do gráfico dos totais individuais por sprint, é o notável que até a sprint 6 havia um quadro estável, apesar de já haver indícios de riscos altos. Porém na sprint 7 e o 8 é perceptível um grande salto, praticamente todos os riscos aumentaram, com foco em 5 em específico: R03, R04, R09, R10 e R11.

- R03   | Falta de participação de algum integrante do projeto 
- R04   | Falta de integração da equipe          
- R09   | Falta de disponibilização de releases para o cliente testar
- R10   | Falta de participação durante as reuniões    
- R11   | Sobrecarga de membros da equipe

#### Risco total
![image](https://github.com/user-attachments/assets/52bd4059-c3d1-4921-bed0-e090aaa68822)

Ao analisar o gráfico geral da probabilidade dos riscos, observa-se um aumento significativo da Sprint 7 para a Sprint 8. Esse aumento abrupto pode é preocupante e pode indicar que o monitoramento dos riscos pode não ter sido completamente eficaz ou estava enviesado. 
O ideal seria um crescimento mais gradual e controlado, refletindo uma gestão de riscos mais equilibrada. O salto substancial pode sugerir que novos problemas surgiram ou que questões importantes foram subestimadas anteriormente.
