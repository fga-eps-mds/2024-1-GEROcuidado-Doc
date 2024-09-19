
# Postmortem 

## Histórico de versões

| Versão | Data       | Descrição             | Autores     |
| ------ | ---------- | --------------------- | ----------- |
| 1.0    | 12/09/2024 | Abertura do documento | [Sebastián Zuzunaga](https://github.com/sebazac332) |
| 1.1    | 18/09/2024 | Adição de informações | [Amanda Nobre](https://github.com/AmandaNbr) |

## Introdução

O presente documento tem como finalidade compartilhar as experiências vividas pela equipe durante o desenvolvimento do projeto, além de promover uma autorreflexão. Também visa auxiliar outras equipes na condução de futuros projetos.

## Condução do projeto

Este projeto foi marcado por diversos desafios, refletidos na opinião unânime da equipe sobre sua complexidade. No início da disciplina, durante a Lean Inception, ficou claro que o que havia sido desenvolvido no semestre anterior (2023.2) não poderia ser aproveitado. Diante disso, tomamos a difícil decisão de recomeçar a implementação do zero.

A primeira release foi entregue com as funcionalidades iniciais, mas, no início da segunda release, enfrentamos outra decisão importante: continuar o desenvolvimento do novo app ou retomar o projeto do semestre anterior. A discussão ressurgiu ao percebermos que poderíamos reutilizar boa parte do que havia sido feito em 2023.2, para que algumas funcionalidades do app rodassem offline, que era uma das principais demandas do cliente.

Após muita reflexão e debate, optamos por dar continuidade ao projeto GeroCuidado 2023.2. Foi necessário parar e recalcular a rota, refazendo o backlog e as histórias de usuário, que tiveram foco na correção de bugs e melhorias, considerando o tempo limitado que restava até o final do projeto.

## Pontos Fortes

- Experiência de como é ter um cliente real
- Resiliência para superar empecilhos
- Entrega do app com funcionalidades offline
- Muitos aprendizados de MDS
  - Tecnologias novas (Git, Docker, React Native)
  - Metodologias

## Pontos Fracos

- Ambiente de desenvolvimento dos membros de MDS.
  - Para conseguir desenvolver para mobile normalmente é necessário um computador com configurações boas.
- Máquina com as especificações mínimas definidas pelo plano de custos.
- Replanejamento do projeto.
- Imprevistos com o time.
- Poucos integrantes de EPS.
- Sobrecarga no fim do projeto.

## Pontos Pendentes

Para fornecer uma base inicial aos colegas do próximo semestre, a equipe compilou uma lista de pendências do projeto.

- Implementação da interação com o fórum (comentários, likes)
- Maior aderência do protótipo, botões e telas levemente diferentes. Ex:<br>
[Header de idoso diferente do que está no app]<br>
![image](https://github.com/user-attachments/assets/2d3a9a13-469c-4a49-8a83-3e58bcd88d37)<br>
[Tela de falha na conexão ao acessar o fórum offline]<br>
![image](https://github.com/user-attachments/assets/6d67e7d2-abb9-4233-8415-783a11c71cfe)

- Funcionalidade de fazer download das métricas e rotina do idoso, o ideal seria fazer de forma que fizesse o download em pdf ou exportasse as informações para serem compartilhadas de forma organizada, entre um determinado intervalo de tempo. Ex: Baixar métricas de pressão sanguínea do último mês; Baixar todas as métricas da última semana.
- **TO-DO: Explicar a parte do endpoint único e como pode ser melhorado**

## Recomendações

Caso seja necessária uma mudança de escopo, é fundamental considerar o tempo necessário para aprender as novas tecnologias envolvidas. Além disso, não se deve negligenciar a comunicação entre as equipes, e é crucial manter a regularidade das reuniões semanais, sem pular nenhuma. Esses fatores são essenciais para garantir que o projeto avance de forma eficaz e coordenada.

O perfeccionismo pode atrapalhar a entrega, pois não é necessário que ela seja perfeita; melhorias podem ser feitas na próxima sprint. O pior erro é não entregar nada.
