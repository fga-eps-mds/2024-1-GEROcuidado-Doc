
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

### Definição de Estimate

Defina uma estimativa de dificuldade (pontuação) para a issue, levando em consideração os seguintes critérios:

| Pontuação | Critérios                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| 1         | Tarefa bem simples, possível de ser feita rapidamente                                            |
| 2         | Tarefa simples que leva algumas horas                                                            |
| 3         | Tarefa que pode levar algumas horas e necessita de alguma pesquisa                               |
| 5         | Tarefa não tão simples, que requer pesquisa e deve levar alguns dias                             |
| 8         | Tarefa complexa, que pode durar a semana toda                                                    |
| 13        | Tarefa muito complexa, provavelmente levará mais que uma sprint; melhor rever e dividir em mais de uma issue |

A pontuação da issue deverá ser votada utilizando a ferramenta de planning poker do ZenHub.

![image](https://user-images.githubusercontent.com/35047444/134027168-e011b3ca-7185-48d2-bcba-0ef0aa8cae68.png)

- **Para issues que envolvem apenas um time:** Todo o time deverá ser adicionado ao planning poker.
- **Para issues que envolvem mais de um time:** Apenas os colaboradores diretamente envolvidos deverão ser adicionados ao planning poker.

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
