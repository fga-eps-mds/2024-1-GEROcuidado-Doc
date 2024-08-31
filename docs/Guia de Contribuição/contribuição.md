
# Guia de Contribuição


## Histórico de Versões

|    Data    | Versão |             Descrição             |                     Autor                      |
|:----------:|:------:|:---------------------------------:|:----------------------------------------------:|
| 12/08/2024 |  1.0   |         Criação do documento      | [Gustavo Abrantes](https://github.com/GustaaSZ) |
| 23/08/2024 |  2.0   |       Atualização do documento    | [Gabriel Monteiro](https://github.com/GabrielSMonteiro) |

## Issues

Ao criar issues, atente-se às seguintes questões:

- **Verifique se já existe uma issue referente ao assunto que você pretende abordar:** Se sim, trabalhe a partir da issue já criada.
- **Título:** Adicione um título que sintetize bem o problema abordado na issue.
- **Descrição:** Adicione uma descrição adequada, de modo que qualquer membro do repositório consiga compreender qual é o problema.
- **Assignees:** Adicione ao menos um responsável (Assignee).
- **Labels:** Adicione as Labels adequadas.
- **Milestone:** Adicione a milestone referente à sprint em que o problema será trabalhado.
- **Estimate:** Adicione uma estimativa de pontuação, conforme as definições descritas neste documento.

## Branches

Padronizar evita confusões e facilita a leitura e a procura por artefatos do projeto. Isso também se aplica à nomenclatura de _branches_. Por padrão, a nomenclatura de _branches_ deve obedecer ao seguinte formato:

```bash
<type>/<branch-name>
```

### Type

O parâmetro _type_ sinaliza o principal tipo de modificação realizada. Por padrão, utilizamos as seguintes palavras-chave:

|   _Type_   |                           Significado                           |
|:----------:|:---------------------------------------------------------------:|
|   _feat_   |              Novas funcionalidades para o usuário               |
|   _fix_    |               Correções de _bugs_ para o usuário                |
|   _docs_   |                  Modificações na documentação                   |
|  _style_   |        Formatação, sem alterações no código de produção         |
| _refactor_ |                Refatoração de código de produção                |
|   _test_   | Adição e refatoração de testes (sem alterar código de produção) |
|  _chore_   |   Atualizações genéricas sem alterações de código de produção   |

### Branch Name

O parâmetro _branch-name_ descreve de forma textual a atividade realizada dentro da _branch_. Por padrão, o nome da _branch_ é escrito em inglês, substituindo os espaços por hífen ("_"). Por exemplo: `Create new tests for user` se torna `create-new-tests-for-user`.

> **Atente-se para a criação de um nome coerente para sua _branch_, a fim de evitar confusões e incoerências.**

### Exemplos

Uma _branch_ para adição de novos testes para um _user_:

```bash
test/create-new-tests-for-user
```

Uma _branch_ para correção de um bug na criação de _user_:

```bash
fix/remove-bug-from-user-creation
```

### Criação de Branches

A partir do repositório desejado:

1. **Atualize seu repositório local buscando por novidades no repositório remoto:**

```bash
git fetch
```

2. **Mude para a branch principal, seja _develop_ ou _main_:**

```bash
git checkout <branch-principal>
```

3. **Sincronize o estado da _branch_ local com o estado da _branch_ remota:**

```bash
git reset --hard <branch-principal>
```

4. **A partir da _branch_ atual, crie a nova _branch_ obedecendo à convenção de nomes:**

```bash
git checkout -b <type>/<branch-name>
```

## Commits

A política de commits deste projeto é baseada no [Conventional Commits v1.0.0](https://www.conventionalcommits.org/pt-br/v1.0.0/).

O Conventional Commits define um conjunto de regras simples para que as mensagens de commit sejam consistentes no histórico de um repositório. Utilizar uma convenção como essa facilita a leitura do histórico, a identificação das mudanças realizadas por um commit e facilita a adoção de ferramentas de automação para gerar changelogs ou release notes.

Por padrão, as mensagens de _commits_ devem seguir o seguinte formato:

```bash
<type>: <subject>
```

### Type

Assim como para as _branches_, _type_ descreve o tipo de modificação contemplada pelo _commit_. Por padrão, utilizamos as seguintes palavras-chave:

|   _Type_   |                           Significado                           |
|:----------:|:---------------------------------------------------------------:|
|   _feat_   |              Novas funcionalidades para o usuário               |
|   _fix_    |               Correções de _bugs_ para o usuário                |
|   _docs_   |                  Modificações na documentação                   |
|  _style_   |        Formatação, sem alterações no código de produção         |
| _refactor_ |                Refatoração de código de produção                |
|   _test_   | Adição e refatoração de testes (sem alterar código de produção) |
|  _chore_   |   Atualizações genéricas sem alterações de código de produção   |

### Subject

O parâmetro _subject_ representa a mensagem que descreve o _commit_, escrita em inglês. Uma boa prática é sempre escrever _subjects_ descritivos, isto é, sempre se preocupando em deixar bem claros os conceitos de ***what*** (o que foi feito) e ***why*** (por que foi feito).

Para clarificar as recomendações aqui mencionadas, confira estes exemplos:

> `Modifies user model`  
> Ao avaliar esta mensagem de commit, o conceito ***what*** é superficial, pois não descreve especificamente o que foi alterado no modelo de usuário. O conceito ***why*** sequer existe.

> `Modifies user's model name field to make it shorter`  
> Ao avaliar esta mensagem de _commit_, quem quer que a leia entenderá o motivo e do que se trata a alteração feita. Tal clareza permite poupar esforço e tempo para entender do que o _commit_ se trata.

## Pull Request

O Pull Request (PR) é a maneira de contribuir para projetos de grupo ou de código aberto (open source).

Por exemplo, um usuário copia um repositório e faz alterações nesse repositório. Agora, ele pode fazer um Pull Request para o repositório original, mas cabe ao mantenedor aceitá-lo ou recusá-lo. É como dizer: "Você poderia aceitar minhas alterações, por favor?"

```bash
git remote
```

![image](https://www.freecodecamp.org/portuguese/news/content/images/2023/05/remote.png)

Depois de identificar o nome do repositório remoto, podemos enviar/fazer um push dessas alterações para o GitHub:

```bash
git push origin <nome_da_branch>
```

Agora, navegue até o repositório no GitHub do projeto, e você verá um botão dizendo **Compare & pull request**. Clique nele.

![image](https://www.freecodecamp.org/portuguese/news/content/images/2023/05/compare.png)

Antes de clicar em **Create pull request**, adicione uma descrição com todos os campos a seguir:

|   Campo            |                                Descrição                                      |
|--------------------|-------------------------------------------------------------------------------|
| **Nomear PR**      | `[#NUMERO_ISSUE] Nome do PR`                                                  |
| **Descrição**      | Insira uma descrição geral do que foi alterado neste PR                       |
| **US**             | Closes `#NUMERO_US`                                                           |
| **Issue**          | Closes `#NUMERO_ISSUE`                                                        |
| **Principais Implementações** | Se for código, descreva alterações relevantes                      |

### Tipos de Mudanças

- [ ] **Bug fix:** Correção que resolve uma issue sem alterar funcionalidades já existentes.
- [ ] **Nova feature:** Adição de uma funcionalidade sem alterar funcionalidades já existentes.
- [ ] **Breaking change:** Mudança que afeta o funcionamento de partes dependentes do código (quando uma dependência crítica ou método é alterado, por exemplo).
- [ ] **Refatoração de código:** Alteração que visa melhorar a qualidade do código sem modificar funcionalidades.
 - [ ] **Documentação**
 - [ ] **Experiência do usuário (UX)**
 - [ ] **Melhoria de desempenho**

**Atenção! Ao fazer um pull request atente-se para:**

- Seguir o template configurado.
- Linkar o PR a sua Issue correspondente.
- Marcar um dos responsáveis para revisão.

### Exemplo de Pull Request

```markdown
[#0] Removendo espaços vazios

## Descrição

- Removendo espaços vazios para evitar erros de compilação.

## Issues

- Closes #1

## Principais Implementações

- Ajustes no código para melhor performance.
```

### Dicas para a criação de um bom PR:

- Divida PRs grandes em PRs menores quando possível.
- Faça um bom título e uma boa descrição para o seu PR.
- Lembre-se de referenciar as issues e/ou user stories associadas ao PR.
- Inclua capturas de tela ou gifs que demonstrem visualmente o que foi feito, se aplicável.

### Análise de Pull Request

Durante a revisão, alguns pontos de atenção são importantes:

- **Nome:** Verifique se a nomenclatura do PR e a descrição estão de acordo com o padrão.
- **Issue:** Certifique-se de que a Issue mencionada seja fechada com o PR.
- **Implementações:** Confirme se as principais implementações mencionadas no PR estão coerentes com a solicitação da Issue.
- **Sugestões:** Se necessário, faça sugestões para melhorar o código.
- **Aprovação:** Caso tudo esteja de acordo, aprove o PR.

## User Stories (US)

As User Stories (US) são uma forma ágil de capturar os requisitos de uma funcionalidade sob a perspectiva do usuário final. Elas descrevem a necessidade do usuário de forma simples e direta, permitindo que o time de desenvolvimento compreenda o objetivo final da funcionalidade.

### Estrutura da US

Cada US deve seguir a estrutura básica:

```markdown
Como <persona>, eu quero <necessidade>, para que <benefício>.
```

**Exemplo:**
```markdown
Como usuário autenticado, eu quero poder redefinir minha senha, para que eu possa acessar minha conta caso eu esqueça a senha atual.
```

### Criação de User Stories

**Ao criar uma US, atente-se aos seguintes pontos:**

1. **Persona:** Identifique o tipo de usuário para o qual a funcionalidade está sendo criada.
2. **Necessidade:** Descreva claramente o que o usuário deseja fazer.
3. **Benefício:** Explique o motivo ou o valor que essa funcionalidade traz para o usuário.
4. **Critérios de Aceitação:** Liste os critérios que precisam ser atendidos para que a US seja considerada completa. Eles servem como um guia para a equipe de desenvolvimento e para o time de QA durante o processo de validação.

### Exemplo de User Story Completa

```markdown
**US01 - Redefinir Senha**

Como usuário autenticado, eu quero poder redefinir minha senha, para que eu possa acessar minha conta caso eu esqueça a senha atual.

**Critérios de Aceitação:**
- O usuário deve poder solicitar a redefinição de senha informando o e-mail cadastrado.
- Um e-mail com um link para redefinição deve ser enviado para o usuário.
- O link deve ser válido por 24 horas.
- O usuário deve poder definir uma nova senha após clicar no link.
- A nova senha deve atender aos critérios de segurança definidos (mínimo de 8 caracteres, incluindo letras maiúsculas, minúsculas e números).

**Estimate:** 5 pontos
```

### Estimativa de Pontuação para US

Assim como as Issues, as US também devem ter uma estimativa de pontuação com base na complexidade e no esforço necessário para a implementação. A pontuação será decidida em conjunto pelo time, utilizando ferramentas como o Planning Poker no ZenHub.

### Criação de Pull Requests para US

Ao concluir a implementação de uma US, crie um Pull Request (PR) seguindo as orientações descritas na seção de Pull Requests deste guia. Certifique-se de:

- Mencionar a US correspondente no título do PR.
- Descrever brevemente as alterações realizadas.
- Incluir as referências às Issues que foram resolvidas durante a implementação da US.
- Adicionar capturas de tela ou GIFs que demonstrem a funcionalidade implementada, se aplicável.

### Revisão de User Stories

Durante a revisão de uma US, preste atenção aos seguintes aspectos:

- **Clareza da US:** A história está clara e compreensível?
- **Critérios de Aceitação:** Todos os critérios foram implementados e validados?
- **Teste:** A funcionalidade foi testada adequadamente?
- **Documentação:** A documentação está atualizada de acordo com a nova funcionalidade?


## Padrões de Código

Manter a consistência de estilo de código ajuda na legibilidade e manutenção do projeto. Alguns pontos a serem considerados incluem:

- **Indentação:** Use espaços ou tabulações consistentes (conforme o padrão do projeto).
- **Nomes de Variáveis:** Prefira nomes descritivos e consistentes.
- **Comentários:** Adicione comentários esclarecedores onde necessário.
- **Linhas em Branco:** Utilize espaços para separar conceitos ou blocos de código.
- **Limpeza:** Evite deixar código comentado sem justificativa ou trechos de código obsoletos.

## Referências

[Commits Convencionais](https://www.conventionalcommits.org/pt-br/v1.0.0/)

[Git branch naming conventions](https://deepsource.io/blog/git-branch-naming-conventions/)

[Gerenciando seus branches com o Git Flow](https://tableless.com.br/git-flow-introducao/)

[Políticas do Repositório](https://github.com/fga-eps-mds/2019.2-Acacia/blob/develop/docs/policies.md)


---
