<h1 align="center">
    <img alt="React RocketShoes" src="https://res.cloudinary.com/andrefer/image/upload/v1596153974/Oh%20My%20ZSH/OMZLogo_BnW_t1q5tm.png"/>
    <br>    
    Oh My ZSH para o Terminal do Windows
</h1>

<h3 align="center">
    Guia para a configuração do Oh My ZSH no Terminal do Windows
</h3><br>

<h2>Instalar o Subsistema Windows para Linux</h2>

Antes de instalar as distribuições do Linux no Windows, você deverá habilitar o recurso [Subsistema do Windows para Linux (WSL)][wsl].

Abra o PowerShell como administrador e execute:

```bash
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
<br>
<h2>Atualizar para o WSL 2</h2>

Para atualizar para o WSL 2, você deve atender aos seguintes critérios:

- Possuir o Windows 10, atualizado para a versão 2004, Build 19041 ou superiores.

- Verifique sua versão do Windows selecionando a tecla do logotipo do Windows + R, digite winver, selecione OK. (Ou digite o comando ver no prompt de comando do Windows). Faça a atualização para a última versão do Windows se o build for anterior ao 19041.

<br>
<h2>Habilite o componente opcional "Plataforma de máquina virtual"</h2>

Antes de instalar o WSL 2, você deve habilitar o recurso opcional "Plataforma de Máquina Virtual".

Abra o PowerShell como administrador e execute:

```bash
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

<strong>Reinicie</strong> o computador para concluir a instalação do WSL e a atualização para o WSL 2.

<br>
<h2>Definir o WSL 2 como sua versão padrão</h2>

Abra o PowerShell como administrador e execute este comando para definir o WSL 2 como a versão padrão ao instalar uma nova distribuição do Linux:

```bash
wsl --set-default-version 2
```
Agora precisamos instalar o [Kernel do Linux][kernel]

<br>
<h2>Atualizando o kernel do WSL 2 Linux</h2>

Faça o download do último pacote de atualização do [kernel do WSL2 Linux][kernelUpdate] para máquinas x64.

<br>
<h2>Instale o pacote de atualização do kernel do Linux</h2>

Para instalar o pacote de atualização do kernel Linux:

1. Execute o pacote de atualização baixado na etapa anterior.

2. Você será solicitado a obter permissões elevadas, selecione 'yes' para aprovar esta instalação.

3. Quando a instalação estiver concluída, você estará pronto para começar a usar o WSL2!

<br>
<h2>Instalar a distribuição do Linux</h2>

- [Ubuntu 16.04 LTS](https://www.microsoft.com/store/apps/9pjn388hp8c9)
- [Ubuntu 18.04 LTS](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
- [Ubuntu 20.04 LTS](https://www.microsoft.com/store/apps/9n6svws3rx71)
- [OpenSUSE Leap 15.1](https://www.microsoft.com/store/apps/9NJFZK00FGKV)
- [SUSE Linux Enterprise Server 12 SP5](https://www.microsoft.com/store/apps/9MZ3D1TRP8T1)
- [SUSE Linux Enterprise Server 15 SP1](https://www.microsoft.com/store/apps/9PN498VPMF3Z)
- [Kali Linux](https://www.microsoft.com/store/apps/9PKR34TNCV07)
- [Debian GNU/Linux](https://www.microsoft.com/store/apps/9MSVKQC78PK6)
- [Fedora Remix para WSL](https://www.microsoft.com/store/apps/9n6gdm4k2hnc)
- [Pengwin](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
- [Pengwin Enterprise](https://www.microsoft.com/store/apps/9N8LP0X93VCP)
- [Alpine WSL](https://www.microsoft.com/store/apps/9p804crf0395)

<br>
<h2>Configurar uma nova distribuição</h2>

Na primeira vez que você iniciar uma distribuição do Linux recém-instalada, uma janela de console será aberta e será solicitado que você aguarde um ou dois minutos para que os arquivos sejam descompactados e armazenados em seu PC. Todas as futuras inicializações deverão levar menos de um segundo.

Em seguida, você precisará criar uma conta de usuário e uma senha para sua nova distribuição do Linux, aconselho colocar o mesmo nome da máquina e senha de login do Windows.

<h2 align="center">
    <img alt="React RocketShoes" src="https://res.cloudinary.com/andrefer/image/upload/v1596155849/Oh%20My%20ZSH/ubuntuinstall_ojsckg.png"/>
</h2>

<br>
<h2>Definir a versão de distribuição para WSL 1 ou WSL 2</h2>

Verifique a versão do WSL atribuída a cada uma das distribuições do Linux instaladas abrindo a linha de comando do PowerShell e inserindo o comando (disponível somente no Windows Build 19041 ou superiores):

```bash
wsl --list --verbose
```

Para definir uma distribuição para ter suporte de qualquer versão do WSL, execute:

```bash
wsl --set-version <distribution name> <versionNumber>
```

Assegure-se de substituir \<distribution name> pelo nome real da sua distribuição e \<versionNumber> pelo número '1' ou '2'. Você pode retornar ao WSL 1 a qualquer momento executando o mesmo comando acima, mas substituindo "2" por "1".

Além disso, se quiser tornar o WSL 2 sua arquitetura padrão, você poderá fazê-lo com este comando:

```bash
wsl --set-default-version 2
```

<br>
<h2>Instalando o ZSH</h2>

Abra o Terminal do Windows e selecione a distro Linux baixada (preferencialmente), se optar pelo Prompt de Comando, PowerShell ou outro, precisará executar o comando:

```bash
 bash
```
Em seguida, execute: 

Ubuntu, Debian & derivatives (Windows 10 WSL | Native Linux kernel with Windows 10 build 1903)

```bash
sudo apt install zsh
```

Digite a senha definida anteriormente e pressione ENTER e, quando for perguntado se você quer continuar, digite "Y".

Com o Zsh instalado deve ser possível você executar:

```bash
zsh --version
```

O resultado deve ser algo parecido com isto: "zsh 5.8 (x86_64-ubuntu-linux-gnu)" (mudando apenas a versão e a distro do Linux)

<br>
<h2>Instalando Oh My Zsh</h2>

Instalando o cURL

```bash
sudo apt-get install curl
```

Para instalar o [Oh My Zsh][omz] você precisa executar o comando abaixo:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Quando for perguntado se você deseja mudar o shell padrão para zsh, digite Y, insira sua senha e pressione ENTER.

<strong>Reinicie</strong> o terminal.

<br>
<h2>Caso a instalação acima do ZSH não funcione, faça:</h2>

<h3>Instalação do Git</h3>

```bash
sudo apt-add-repository ppa:git-core/ppa
sudo apt-get update
sudo apt-get install git
```

<h3>Instalar Zsh e Oh My Zsh</h3>

- Instalação Zsh
```bash
sudo apt-get install zsh
```
- Instalação Oh My Zsh
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
<strong>Reinicie</strong> o terminal.

<br>
<h2>Configurar e executar Oh My Zsh</h2>

Se você optar por usar uma shell diferente das disponibilizadas nas distros do Linux precisará e usar os comandos:

```bash
 bash
```
E então usar o comando:
```bash
zsh
```

<br>
<h2>Instalando Spaceship</h2>

Para um melhor funcionamento, instale a fonte [Fira Code][firaCode] e o tema [Dracula][dracula] no [Terminal do Windows][draculaWT] (opcional).

Vamos começar clonando o repositório do Spaceship em nossa pasta de themes do Oh My Zsh (é necessário ter instalado o Git pra isso):

```bash
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
```

Agora vamos criar um link simbólico para o arquivo do tema do Spaceship na pasta dos temas do Oh My Zsh:

```bash
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

Precisamos abrir o arquivo "~/.zshrc" para alterar a variável "ZSH_THEME", para isto, execute:

```bash
nano ~/.zshrc
```

Agora você deve alterar a variável ZSH_THEME, ficando desta forma:

```bash
ZSH_THEME="spaceship"
```

Para sair do arquivo pressione CTRL + X, depois Y e por último ENTER.

<strong>Reinicie</strong> o terminal.

<br>
<h2>Configurações adicionais (opcional)</h2>

<h3>Configurando Spaceship</h3>

Por mais que seja muito interessante mostrar as versões do Node, Docker e outros itens no nosso terminal geralmente isso consome processamento e pode tornar mais lento o carregamento de pastas, por isso é interesssante desabilitar a maioria dessas opções.

No fim do arquivo "~/.zshrc" adicione o seguinte conteúdo:

```bash
SPACESHIP_PROMPT_ORDER=(
  user          # Username section
  dir           # Current directory section
  host          # Hostname section
  git           # Git section (git_branch + git_status)
  hg            # Mercurial section (hg_branch  + hg_status)
  exec_time     # Execution time
  line_sep      # Line break
  vi_mode       # Vi-mode indicator
  jobs          # Background jobs indicator
  exit_code     # Exit code section
  char          # Prompt character
)
SPACESHIP_USER_SHOW=always
SPACESHIP_PROMPT_ADD_NEWLINE=false
SPACESHIP_CHAR_SYMBOL="❯"
SPACESHIP_CHAR_SUFFIX=" "
```

Para sair do arquivo pressione CTRL + X, depois Y e por último ENTER.

<strong>Reinicie</strong> o terminal.

<h3>Plugins do ZSH</h3>

Para instalar plugins precisamos configurar o ZInit, ferramenta que facilita a instalação e remoção de plugins no Zsh.

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zinit/master/doc/install.sh)"
```

Quando for solicitado, digite "y" e em seguinda ENTER.

Após essa instalação, vamos abrir o arquivo "~/.zshrc" novamente e abaixo da linha "### End of ZInit's installer chunk" que foi adicionada automaticamente no arquivo, adicionamos:

```bash
zinit light zdharma/fast-syntax-highlighting
zinit light zsh-users/zsh-autosuggestions
zinit light zsh-users/zsh-completions
```

<strong>Reinicie</strong> o terminal para concluir a instalação.

- <strong>zdharma/fast-syntax-highlighting</strong>: Adiciona syntax highlighting na hora da escrita de comandos que facilita principalmente em reconhecer comandos que foram digitados de forma incorreta;
- <strong>zsh-users/zsh-autosuggestions</strong>: Sugere comandos baseados no histórico de execução conforme você vai digitando;
- <strong>zsh-users/zsh-completions</strong>: Adiciona milhares de completitions para ferramentas comuns como Yarn, Homebrew, NVM, Node, etc, para você precisar apenas apertar TAB para completar comandos.

<h2>Terminal no VSCode</h2>

Para utilizar o Oh My ZSH no VS Code, adicione a seguinte linha no arquivo "settings.json":

```json
"terminal.integrated.shell.windows": "C:\\Windows\\System32\\bash.exe",
```



[wsl]: https://docs.microsoft.com/pt-br/windows/wsl/install-win10
[kernel]: https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel
[kernelUpdate]: https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
[omz]: https://ohmyz.sh/#install
[dracula]: https://draculatheme.com/ 
[draculaWT]: https://draculatheme.com/windows-terminal
[firaCode]: https://github.com/tonsky/FiraCode/releases

<h3>Fontes:</h3> 

1. [Guia de instalação do Subsistema Windows para Linux para Windows 10](https://docs.microsoft.com/pt-br/windows/wsl/install-win10)

2. [Atualizando o kernel do WSL 2 Linux](https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel)

3. [Installing ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)

4. [Terminal com Oh My Zsh, Spaceship, Dracula e mais](https://blog.rocketseat.com.br/terminal-com-oh-my-zsh-spaceship-dracula-e-mais/)

5. [Hyper no Windows10 : Instalação, configuração, integração VSCode](https://medium.com/collabcode/hyper-no-windows10-instala%C3%A7%C3%A3o-configura%C3%A7%C3%A3o-integra%C3%A7%C3%A3o-vscode-cf80ad4a696d)

6. [Oh My ZSH](https://ohmyz.sh/#install)

7. [Spaceship](https://denysdovhan.com/spaceship-prompt/docs/Options.html?q=#exit-code-exit_code)

Made by André Fernandes :wave: [Get in touch!](https://www.linkedin.com/in/andrefbispo/)
