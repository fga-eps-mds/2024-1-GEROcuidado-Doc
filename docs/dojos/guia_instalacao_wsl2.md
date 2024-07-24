# Guia de instalação WSL2

## Histórico de versões

|    Data    | Versão |      Descrição       |                    Autor                     |
|:----------:|:------:|:--------------------:|:--------------------------------------------:|
| 05/04/2024 |  1.0   | Criação do documento | [Amanda Nobre](https://github.com/AmandaNbr) |

### Habilitando WSL

Utilizaremos o Windows Subsystem for Linux *(versão 2)* como nosso ambiente de desenvolvimento. O primeiro passo é **habilitar o WSL** no seu computador. Para isso, abra uma janela do PowerShell com permissões de administrador e execute esse comando:

> **Atenção**: Ao executar o comando abaixo, se o processador for AMD, o seguinte erro pode acontecer `Please enable the Virtual Machine Platform Windows feature and ensure virtualization is enabled in the BIOS`. Para solucionar basta acessar a BIOS e ativar o **SVM Mode**.<br>

```bash
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

### Habilitando recurso de Máquina Virtual

Agora, precisamos habilitar o recurso de máquina virtual no Windows. Para isso, execute o comando abaixo:

```bash
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

Pronto! Já habilitamos o WSL e o recurso de máquina virtual. **É necessário reiniciar o computador nesse momento para continuar com a instalação.**

### Atualizando kernel do linux para podermos utilizar o WSL 2

Agora, vamos precisar **atualizar o kernel do Linux** para podermos utilizar a versão 2 do WSL. Para isso, é necessário que o seu Windows 10 esteja na **versão 1903 ou maior**. Para verificar qual a versão instalada na sua máquina, basta abrir uma janela do Prompt de Comando(CMD) e executar o comando `ver`.  Aparecerá a versão instalada na sua máquina.

Ex: Microsoft Windows [versão 10.0.**19042**.746] (Número que está em negrito corresponde a versão do Windows 10).

Cumprindo o requisito de versão acima, basta agora **baixar o arquivo de atualização** clicando no link abaixo e instalar o mesmo:

[Atualização WSL2](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

### Definindo WSL 2 como versão padrão

Abra uma janela do PowerShell com permissões de administrador e execute o seguinte comando para definir o WSL2 como padrão para instalações de distribuições do Linux.

```bash
wsl --set-default-version 2
```

### Instalar Ubuntu no WSL

Abra a loja de aplicativos do Windows 10 (Microsoft Store) e procure por Ubuntu:

![Captura_de_Tela_(2)](https://user-images.githubusercontent.com/25483313/117460804-46b64a80-af23-11eb-9889-c831c1c12a4d.png)

![Untitled](https://user-images.githubusercontent.com/25483313/117460889-5e8dce80-af23-11eb-85f7-cbe27c65de47.png)

Agora, **Instale** essa aplicação chamada de **Ubuntu.**

![Untitled 1](https://user-images.githubusercontent.com/25483313/117460875-5b92de00-af23-11eb-9fc1-d16be17099a5.png)

**Após instalar, execute o Ubuntu instalado.** Irá abrir uma janela pedindo para você criar uma conta de usuário padrão o Ubuntu. Insira seu nome de usuário e depois a senha que deseja. **Feito isso, Já temos o WSL2 configurado e com o Ubuntu instalado!**
