# Como contribuir

## Histórico de versões

|    Data    | Versão |      Descrição       |                    Autor                     |
|:----------:|:------:|:--------------------:|:--------------------------------------------:|
| 05/04/2024 |  1.0   | Criação do documento | [Amanda Nobre](https://github.com/AmandaNbr) |

## Issues

Ao criar issues atente-se as seguintes questões:

- Já existe issue referente ao assunto que você pretende abordar na sua? Se sim, trabalhe a partir da issue já criada
- Adicione um título que sintetize bem o problema abordado na issue
- Adicione uma descrição adequada, de modo que qualquer membro do repositório consiga compreender qual é o problema
- Adicione ao menos um Assignee
- Adicione as Labels adequadas
- Adicione a milestone referente a sprint em que o problema será trabalhado
- Adicione um Estimate segundo as definições descritas nesse documento

### Definição de Estimate

Deve-se definir uma estimativa de dificuldade (pontuação) à issue em questão, levando em consideração os seguintes critérios:

Pontuação | Critérios
----------|-------------------------------------------------------------------------------------------------------------
1         | Tarefa bem simples, é possível ser feita em até 1h
2         | Tarefa simples que leva algumas horas
3         | Tarefa que pode levar algumas horas e necessita de alguma pesquisa
5         | Tarefa não tão simples, precisa de pesquisa e deve levar alguns dias
8         | Tarefa complexa, pode durar a semana toda
13        | Tarefa muito complexa, provavelmente levará mais que uma sprint, melhor rever e dividir em mais de uma issue

A pontuação da issue deverá ser levada a votação utilizando a ferramenta de planning poker do zenhub.

![image](https://user-images.githubusercontent.com/35047444/134027168-e011b3ca-7185-48d2-bcba-0ef0aa8cae68.png)

- Para issues que envolvem apenas um time, todo o time deverá ser adicionado ao planning poker.
- Para issues que envolvam mais de um time, apenas os colaboradores deverão ser adicionados ao planning poker.

## Branches

Padronizar evita confusões e torna mais fácil a leitura e a procura por artefatos do projeto, e isso também se aplica à nomenclatura de _branches_. Por padrão, a nomenclatura de _branches_ deve obedecer o seguinte formato:

`<type>/<branch-name>`

### Type

O parâmetro _type_ sinaliza qual o principal tipo de modificação realizada. Por padrão, utilizamos as seguintes palavras chaves:
|   _Type_   |                           Significado                           |
|:----------:|:---------------------------------------------------------------:|
|   _feat_   |              Novas funcionalidades para o usuário               |
|   _fix_    |               Correções de _bugs_ para o usuário                |
|   _docs_   |                  Modificações na documentação                   |
|  _style_   |        Formatação, sem alterações no código de produção         |
| _refactor_ |                Refatoração de código de produção                |
|   _test_   | Adição e refatoração de testes (sem alterar código de produção) |
|  _chore_   |   Atualizações genéricas sem alterações de código de produção   |

### Branch name

O parâmetro _branch-name_ descreve de forma textual a atividade realizada dentro da _branch_. Por padrão, o nome da _branch_ é escrito em inglês substituindo os espaços por hífen "_-_". Por exemplo: `Create new tests for user`  se torna `create-new-tests-for-user`.

> Atente-se para a criação de um nome coerente para sua _branch_, a fim de evitar confusões e incoerências.

### Exemplos

Uma _branch_ para adição de novos testes para a um _user_:
> test/create-new-tests-for-user

Uma _branch_ para correção de um bug na criação de _user_:
> fix/remove-bug-from-user-creation

### Criação de Branches

A partir do repositório desejado:

1. Atualize seu repositório local buscando por novidades no repositório remoto.
```bash
git fetch
```

2. Mude para a branch principal, seja _develop_ ou _main_.
```bash
git checkout _branch-principal_
```

3. Sincronize o estado da _branch_ local com o estado da _branch_ remota.
```bash
git reset --hard _branch-principal_
```

4. A partir da _branch_ atual, crie a nova _branch_ obedecendo a convenção de nomes.
```bash
git checkout -b <type>/<branch>
```

## Commits

A política de commits desse projeto é baseada no
[Conventional Commits v1.0.0](https://www.conventionalcommits.org/pt-br/v1.0.0/).

Conventional Commits define um conjunto de regras simples para que as mensagens
commit sejam consistentes no histórico de um repositório. Utilizar uma convenção
como essa facilita a leitura do histórico, a identificação das mudanças
realizadas por um commit e facilita a adoção de ferramentas de automação para
gerar changelogs ou release notes.

Por padrão, as mensagens de _commits_ devem seguir o seguinte formato:

```bash
<type>: <subject>
```

### Type
Assim como para as _branches_, _type_ descreve o tipo da modificação contemplada pelo _commit_. Por padrão, utilizamos as seguintes palavras chaves:
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

O parâmetro _subject_ representa a mensagem que descreve o _commit_ escrita em inglês. Uma boa prática que diz respeito a _commits_ é a de sempre escrever _subjects_ descritivos, isto é, sempre se preocupando em deixar bem claro os conceitos ***what*** e ***why***.

Para clarificar as recomendações aqui mencionadas, confira estes exemplos:
> `Modifies user model` <br>
> Ao avaliar esta mensagem de commit, o conceito ***what*** é superficial, pois não descreve especificamente o que foi alterado na model user.
> Já o conceito ***why*** sequer existe.

> `Modifies user's model name field to make it shorter` <br>
> Ao avaliar esta mensagem de _commit_, quem quer que a leia entenderá o motivo, e do que se trata a alteração feita. Tal coisa permite poupar esfoço e tempo para entender do que o _commit_ se trata.


## Pull Request

Ao fazer um pull request atente-se para:

- Seguir o template configurado.
- Linkar o PR a sua Issue correspondente.
- Marcar um dos responsáveis para revisão.

## Referências

[Commits Convencionais](https://www.conventionalcommits.org/pt-br/v1.0.0/)

[Git branch naming conventions](https://deepsource.io/blog/git-branch-naming-conventions/)

[Gerenciando seus branches com o Git Flow](https://tableless.com.br/git-flow-introducao/)

[Políticas do Repositório](https://github.com/fga-eps-mds/2019.2-Acacia/blob/develop/docs/policies.md)