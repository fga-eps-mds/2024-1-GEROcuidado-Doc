
# Dojô Git / GitHub

## Introdução

### Git
Git é um **sistema de controle de versão distribuído** usado para rastrear alterações no código fonte durante o desenvolvimento de software.
- Permite que vários desenvolvedores trabalhem simultaneamente no mesmo projeto
- Audita as alterações feitas em arquivos específicos ao longo do tempo.
- Permite que os desenvolvedores revertam para versões anteriores, criem novas funcionalidades em paralelo e colaborem de maneira eficaz.

### GitHub:
GitHub é uma **plataforma de hospedagem** baseada na web para projetos Git, fornecendo uma interface visual para o controle de versão e colaboração em equipe.

Ele permite que os desenvolvedores hospedem seus repositórios Git remotamente na nuvem e fornece recursos adicionais, como rastreamento de problemas, controle de acesso, integração contínua e muito mais.

## Conceitos chave

### Commit:
Um commit no Git é uma operação na qual as alterações feitas em arquivos específicos são salvas no repositório **local** Git.
- Cada commit é acompanhado de uma mensagem que descreve as alterações feitas, fornecendo contexto sobre o que foi modificado.
- Commits ajudam a rastrear e documentar o progresso do desenvolvimento ao longo do tempo.

### Branch:
Uma branch no Git é uma ramificação independente do código fonte principal (geralmente chamado de branch "master" ou "main").

As branches permitem que os desenvolvedores trabalhem em novas funcionalidades ou correções de bugs sem interferir no código principal.

Depois que as alterações em uma branch são concluídas e testadas, elas podem ser mescladas de volta a branch principal por meio de um processo chamado de "merge".

### Merge:
Merge é o processo de combinar as alterações de uma branch em outra.

Por exemplo, você pode ter uma branch de desenvolvimento onde as novas funcionalidades são adicionadas e, quando estiverem prontas, você pode mesclá-las de volta para a branch principal (master ou main).

### Pull Request (Pedido de Pull):
Um pull request é uma solicitação feita por um colaborador de um repositório Git para incorporar suas alterações em uma branch específica desse repositório.

Geralmente, os pull requests são usados em projetos colaborativos para revisão de código e integração de novas funcionalidades ou correções de bugs. Os mantenedores do projeto podem revisar as alterações propostas, fazer comentários e, eventualmente, mesclar o pull request se estiverem satisfeitos com as alterações.

### Como funciona o GitHub:
O GitHub funciona como um repositório remoto para projetos Git. Os desenvolvedores podem enviar ("push") seus commits para o GitHub e colaborar com outros desenvolvedores em um projeto específico. Eles podem criar branches, abrir pull requests, revisar código, discutir alterações e mesclar alterações no código principal.

![image](https://hermes.dio.me/articles/cover/4c719bca-7cb6-4827-b59b-a0d0fe75673a.png)

---

## Comandos básicos

### Configuração Inicial

Antes de começar, é importante configurar o Git com suas informações pessoais

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@example.com"
```
Essas configurações serão usadas para identificar os autores dos commits que você criar.

### Inicializando um Repositório

Para começar a usar o Git em um projeto, é necessário inicializar um repositório.

```bash
git init
```

Esse comando cria um novo repositório Git no diretório atual.

### Clonando um Repositório

É possível usar um repositório já criado no github e copiá-lo para sua máquina:

```bash
git clone _url-do-repositorio.git_
```

### Adicionando Arquivos

Após inicializar ou clonar um repositório, você pode adicionar e modificar arquivos para serem rastreados pelo Git.

```bash
git add nome_do_arquivo
```

Esse comando adiciona um arquivo específico ao próximo commit. Você também pode usar git add . para adicionar todos os arquivos modificados.

### Fazendo um Commit

Quando você tiver arquivos prontos para serem registrados no histórico do Git, você pode fazer um commit.

```bash
git commit -m "Mensagem do commit"
```

Esse comando cria um novo commit com as alterações adicionadas anteriormente. A mensagem do commit deve descrever as alterações realizadas.

### Enviando commits para um repositório remoto

```bash
git push nome_remoto nome_branch
```

Esse comando envia seus commits locais para um repositório remoto específico.

### Obtendo alterações de um repositório remoto

```bash
git pull nome_remoto nome_branch
```

Esse comando obtém as alterações mais recentes de um repositório remoto e as mescla em sua branch local.

### Verificando o Status

A qualquer momento, você pode verificar o status atual do seu repositório.

```bash
git status
```

Esse comando mostra o status atual do repositório, incluindo arquivos modificados, arquivos adicionados e branch atual.

### Visualizando o Histórico de Commits

Você pode visualizar o histórico de commits no repositório.

```bash
git log
```

Esse comando mostra uma lista de commits no repositório, exibindo informações como autor, data, hora e mensagem do commit.

### Atualizando a branch atual

```bash
git fetch
```

Esse comando é usado para buscar todas as alterações feitas em um repositório remoto para o seu repositório local.
Diferentemente do comando `git pull`, o git fetch apenas baixa as alterações para o seu repositório local, mas não as mescla automaticamente.

### Listando todas as branches

```bash
git branch
```

Esse comando lista todas as branches existentes no repositório. A branch atual é destacada com um asterisco.

### Criando uma nova branch

```bash
git branch nome_da_branch
```

Esse comando cria uma nova branch com o nome especificado, mas não muda para essa branch.

### Mudando para uma branch

```bash
git checkout nome_da_branch
```

Esse comando altera a branch atual para a branch especificada.

### Criando e mudando para uma nova branch

```bash
git checkout -b nome_da_branch
```

Esse comando cria uma nova branch com o nome especificado e imediatamente muda para essa branch.

### Excluindo uma branch

```bash
git branch -d nome_da_branch
```

Esse comando exclui a branch especificada. Certifique-se de estar em outro branch antes de excluí-la.

## Gerenciando Conflitos de Merge

Ao mesclar branches ou obter alterações de um repositório remoto, podem ocorrer conflitos. Veja como lidar com eles:

### Resolvendo conflitos de merge

Abra os arquivos com conflitos e edite-os manualmente para resolver as diferenças.

Após resolver os conflitos, adicione os arquivos modificados usando git add nome_do_arquivo.

Faça um novo commit para finalizar o processo de merge.

### Rebase interativo

```bash
git rebase -i commit_referencia
```

Esse comando permite reorganizar, editar ou combinar commits antes deles serem adicionados ao histórico principal.

### Cherry-pick

```bash
git cherry-pick commit_referencia
```

Esse comando permite aplicar um commit específico a um branch diferente.

---

## Vamos partir para a prática!

Agora a ideia é partir para a prática e usar os comandos aprendidos para fazer commits e pull requests!

- Criar um repositório novo

- Adicionar os participantes

**Todos devem fazer**

- Clonar o repositório

- Criar um arquivo _nome-sobrenome.md_ com sua matrícula dentro.

- Verificar as mudanças

- Adicionar a mudança ao commit

- Commitar na branch

- Conferir as mudanças no repositório local

- Puxar as mudanças feitas pelos colegas do repositório remoto para o local

---

- Criar uma branch _nome-sobrenome_

- Alterar o arquivo com seu nome

- Verificar a mudança

- Adicionar a mudança

- Commitar na sua branch

- Conferir que sua branch apareceu no repositório remoto e aparece a opção para criar um PR

- Criar o PR com um título, descrição e adicionando alguém para revisar

**Extra**

- Criar um conflito e mostrar a resolução
