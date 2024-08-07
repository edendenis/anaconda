# Como configurar/instalar/usar o `Anaconda` no `Linux Ubuntu`

## Resumo

Neste documento estão contidos os principais comandos e configurações para configurar/instalar/usar o `Anaconda` no `Linux Ubuntu`.

## _Abstract_

_In this document are contained the main commands and settings to check for configure/install/use the `Anaconda` on `Linux Ubuntu`._

### Construído com

Esta seção deve listar todas as principais estruturas/bibliotecas usadas para inicializar seu projeto. Deixe quaisquer complementos/plugins para a seção de agradecimentos. Aqui estão alguns exemplos.

* [![Python 3.8](https://img.shields.io/badge/Python%203.8-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)

* [![Anaconda](https://img.shields.io/badge/Anaconda-44A833?style=flat-square&logo=anaconda&logoColor=white)](https://www.anaconda.com/)

* [![Jupyter Collaboration](https://img.shields.io/badge/Jupyter%20Collaboration-F37626?style=flat-square&logo=Jupyter&logoColor=white)](https://jupyter.org/)

<p align="right">(<a href="#readme-top">voltar ao topo</a>)</p>


## Descrição [2]

### `Anaconda`

O `Anaconda` é uma plataforma de código aberto amplamente utilizada por cientistas de dados e engenheiros de aprendizado de máquina. Ele oferece um ambiente de desenvolvimento integrado que simplifica a gestão de pacotes, a criação de ambientes virtuais e o acesso a uma vasta coleção de bibliotecas de análise de dados e aprendizado de máquina. Além disso, o `Anaconda` inclui o `Jupyter Notebook`, uma ferramenta popular para análise de dados interativa e documentação. Essa plataforma é valiosa para profissionais que trabalham com ciência de dados, permitindo-lhes organizar seus projetos, garantir a compatibilidade entre bibliotecas e facilitar a colaboração em equipes de análise de dados.

## 1. Como configurar/instalar/usar o `Anaconda` no `Linux Ubuntu` [1]

### 1.1 Atualizar o Sistema Operacional (SO)

1. Abra o `Terminal Emulator`. Você pode fazer isso pressionando: `Ctrl + Alt + T`


2. Certifique-se de que seu sistema esteja limpo e atualizado.

    2.1 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando: `sudo apt clean` 
    
    2.2 Remover pacotes `.deb` antigos ou duplicados do cache local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando: `sudo apt autoclean`

    2.3 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando: `sudo apt autoremove -y`

    2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`: `sudo apt update`

    2.5 **Corrigir pacotes quebrados**: Isso atualizará a lista de pacotes disponíveis e tentará corrigir pacotes quebrados ou com dependências ausentes: `sudo apt --fix-broken install`

    2.6 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando: `sudo apt clean` 
    
    2.7 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:  `sudo apt list --upgradable`

    2.8 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update`. Digite o seguinte comando e pressione `Enter`: `sudo apt full-upgrade -y`
    

### 1.3 Para instalar o `Python`

#### 1.3.1 `Python 3.8.10`

Para instalar o `Python 3.8.10` a partir do arquivo `Python-3.8.10.tar.xz`, você precisará seguir alguns passos no `Terminal Emulator` do `Linux`. Aqui está um guia passo a passo:

1. **Baixe o arquivo:** Primeiro, você precisa ter o arquivo `Python-3.8.10.tar.xz`. Se já o possui, ótimo. Caso contrário, você pode baixá-lo do site oficial do Python ou de um repositório confiável.

2. **Extraia o arquivo:** Abra um terminal e navegue até o diretório onde o arquivo `Python-3.8.10.tar.xz` está localizado. Você pode usar o comando tar para extrair o arquivo com o seguinte comando: `tar -xf Python-3.8.10.tar.xz`

3. **Navegue até o diretório extraído:** Depois de extrair o arquivo, um diretório chamado `Python-3.8.10` será criado. Navegue até esse diretório usando o comando: `cd Python-3.8.10`

4. **Prepare o ambiente para a compilação:** Antes de compilar o `Python`, você precisa instalar algumas dependências. Dependendo da sua distribuição Linux, o comando pode variar. Para sistemas baseados em Debian/Ubuntu, você pode instalar as dependências necessárias com:

    ```
    sudo apt autoclean
    sudo apt autoremove
    sudo apt update -y
    sudo apt autoremove
    sudo apt autoclean
    sudo apt list --upgradable
    sudo apt full-upgrade
    sudo apt-get install -y build-essential libssl-dev zlib1g-dev libncurses5-dev libncursesw5-dev libreadline-dev libsqlite3-dev libgdbm-dev libdb5.3-dev libbz2-dev libexpat1-dev liblzma-dev tk-dev libffi-dev
    ```

5. **Configure o Python para instalação:** Dentro do diretório `Python-3.8.10`, configure o Python para a instalação com o comando: `./configure --enable-optimizations`

    O argumento `--enable-optimizations` ajuda a otimizar o `Python`, mas torna o processo de compilação mais demorado.

6. **Compile e instale o Python:** Após configurar, compile o código fonte e instale-o com os seguintes comandos:

    ```
    make -j 8 # Onde `8` é o número de núcleos que você deseja usar para a compilação
    sudo make altinstall
    ```

    Usar `make altinstall` em vez de `make install` previne que esta versão do `Python` substitua a versão padrão do sistema.

7. **Verifique a instalação:** Após a instalação, verifique se o `Python` foi instalado corretamente com o comando: `python3.8 --version`

Se tudo correu bem, este comando deve retornar a versão do `Python` que você acabou de instalar.

Esses passos devem ajudá-lo a instalar o `Python 3.8.10` no seu sistema Linux. Note que as etapas específicas podem variar ligeiramente dependendo da sua distribuição `Linux`.


#### 1.3.2 `Python 3.11`

Para instala o `Python 3.11` no `Linux Ubuntu` através do `Terminal Emulator`, você pode seguir os seguintes passos:

3. Instale as dependências necessárias para compilar o Python: `sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev libbz2-dev -y`

4. Faça o download do código-fonte do Python 3.11 no site oficial do `Python`: `wget https://www.python.org/ftp/python/3.11.0/Python-3.11.0.tgz`

5. **Extraia o arquivo `tar.gz` baixado:** `tar -xf Python-3.11.0.tgz`

6. **Navegue até o diretório do código-fonte:** `cd Python-3.11.0`

7. **Configure a compilação do Python:** `./configure --enable-optimizations`

8. **Compile o `Python 3.11`:** `make -j$(nproc)`

9. **Instale o Python recém-compilado:** `sudo make altinstall`

10. O `Python 3.11` deve estar instalado no seu sistema. Você pode verificar a versão do `Python` instalada usando o seguinte comando: `python3.11 --version`

Isso deve exibir a versão `3.11` do `Python`. Agora você pode usar o `Python` `3.11` no seu sistema `Linux Ubuntu`.

### 1.3 Para configurar/instalar/usar o `Anaconda`

#### 1.3.1 Configurar/Instalar/Usar na conta do usuário (recomendado para usuários iniciantes)

Para configurar/instalar/usar o `Anaconda`, você pode seguir estas etapas:

1. Navegue até o diretório onde o arquivo `.sh` está localizado: Use o comando `cd` para navegar até o diretório onde o arquivo `.sh` está localizado. Por exemplo, se o arquivo `.sh` estiver na sua pasta `Downloads`, você pode usar o seguinte comando: `cd ~/Downloads`

2. Torne o arquivo `.sh` executável: Por padrão, os arquivos `.sh` não são executáveis diretamente. Para torná-lo executável, use o comando `chmod +x <nome_do_arquivo>.sh`. Por exemplo: `sudo chmod +x Anaconda3-2023.09-0-Linux-x86_64.sh`

3. Execute o arquivo `.sh`: Agora que o arquivo `.sh` é executável, você pode executá-lo usando o seguinte comando: `./Anaconda3-2023.09-0-Linux-x86_64.sh`

    Certifique-se de substituir `"nome_do_arquivo.sh"` pelo nome real do arquivo `.sh` que você deseja instalar.

    **Siga as instruções**: Dependendo do que o arquivo `.sh` faz, ele pode abrir um instalador ou realizar alguma ação específica. Siga as instruções apresentadas no `Terminal Emulator` para concluir a instalação.

    3.1 Antes do término do processo de instalação, ler a Seção 2: **Comandos para habilitar/desabilitar a inicialização do ambiente `base` junto com o `Terminal Emulator`**


#### 1.3.2 Configurar/Instalar/Usar para acesso a todos (**NÃO** recomendado para usuários iniciantes)

Para configurar/instalar/usar o `Anaconda`, você pode seguir estas etapas:

1. Navegue até o diretório onde o arquivo .sh está localizado: Use o comando `cd` para navegar até o diretório onde o arquivo `.sh` está localizado. Por exemplo, se o arquivo `.sh` estiver na sua pasta Downloads, você pode usar o seguinte comando: `cd ~/Downloads`

2. Torne o arquivo `.sh` executável: Por padrão, os arquivos `.sh` não são executáveis diretamente. Para torná-lo executável, use o comando `chmod +x <nome_do_arquivo>.sh`. Por exemplo: `sudo chmod +x Anaconda3-2023.09-0-Linux-x86_64.sh`

3. Execute o arquivo `.sh`: Agora que o arquivo `.sh` é executável, você pode executá-lo usando o seguinte comando: `sudo ./Anaconda3-2023.09-0-Linux-x86_64.sh`

    Certifique-se de substituir `"nome_do_arquivo.sh"` pelo nome real do arquivo `.sh` que você deseja instalar.

    **Siga as instruções**: Dependendo do que o arquivo `.sh` faz, ele pode abrir um instalador ou realizar alguma ação específica. Siga as instruções apresentadas no terminal para concluir a instalação.

    Use o `sudo` se quiser instalar em uma pasta que seja acessível para todos os usuários, porém, é mais difícil de configurar e pode dar conflitos com outras aplicações, como por exemplo, o `zsh` caso este não seja configurado com o caminho correto. Sem o `sudo`, quando se configura outras aplicações, estas, em geral, reconhecer a instalação na pasta do usuário.

    3.1 Quando solicitar o caminho do arquivo, caso queira, pode ser instalado em: `/opt/anaconda3`

    3.1.1 **Adicione o caminho do `Anaconda` ao `PATH` globalmente:** Para tornar o `Anaconda` disponível para todos os usuários, você precisa adicionar o caminho do `Anaconda` ao arquivo de perfil global. Abra o arquivo `/etc/profile` com um editor de texto de sua escolha (por exemplo, `sudo nano /etc/profile`) e adicione a seguinte linha no final do arquivo: `export PATH="/opt/anaconda3/bin:$PATH"`

    Salve o arquivo e feche o editor de texto.

    3.2 Antes do término do processo de instalação, ler a Seção 2: **Comandos para habilitar/desabilitar a inicialização do ambiente `base` junto com o `Terminal Emulator`**

Agora, o `Anaconda` deve estar instalado e disponível para todos os usuários do sistema. Eles podem acessar o `Conda` e seus ambientes virtualizados usando o comando `conda` no `Terminal Emulator`.


## 2. Comandos para habilitar/desabilitar a inicialização do ambiente `base` junto com o `Terminal Emulator`

1. No momento da instalação, irá aparecer a seguinte pergunta na qual você pode habilitar ou desabilitar o ambiente `base`, leia com atenção, pois possui os comandos, tanto para habilitar, como para desabilitar:

```
Do you wish to update your shell profile to automatically initialize conda?
This will activate conda on startup and change the command prompt when activated.
If you'd prefer that conda's base environment not be activated on startup,
run the following command when conda is activated:

conda config --set auto_activate_base false

You can undo this by running `conda init --reverse $SHELL`? [yes|no]
[no] >>> 
```

Responda `no` para **NÃO** desfazer o comando inicializar o ambiente `(base)` ao abrir o `Terminal Emulator`.

2. **Atualize as configurações de ambiente:** Para que as alterações no arquivo de perfil entrem em vigor, recarregue as configurações de ambiente executando o seguinte comando: `source /etc/profile`

Agora, o `Anaconda` deve estar instalado e disponível para todos os usuários do sistema. Eles podem acessar o `Conda` e seus ambientes virtualizados usando o comando `conda` no `Terminal Emulator`.


### 2.2 Iniciar o `conda` com o comando `conda init`

Vamos revisar e ajustar o procedimento para garantir que tudo esteja configurado corretamente:

1. **Verifique o arquivo de inicialização do _shell_**: Verifique se o caminho para o `Conda` está corretamente configurado no seu arquivo de inicialização do _shell_ (`~/.bashrc` ou `~/.zshrc`). Vamos garantir que o caminho esteja adicionado corretamente. Para editar o arquivo `~/.bashrc` se estiver usando `Bash`: `nano ~/.bashrc`

    1.1 Ou para editar o arquivo `~/.zshrc` se estiver usando `Zsh`: `nano ~/.zshrc`

2. Certifique-se de que a linha para adicionar o caminho do `Conda` esteja presente e sem comentários: `export PATH="/home/edenedfsls/anaconda3/bin:$PATH"`

    Salve e feche o arquivo após adicionar essa linha.

3. **Recarregue as configurações do shell**: Após salvar as alterações no arquivo de inicialização do _shell_, recarregue as configurações do _shell_ para aplicar as mudanças:

```
source ~/.bashrc  # Para Bash
source ~/.zshrc   # Para Zsh
```

4. **Inicialize o `Conda` novamente**: Execute o comando `conda init` novamente para garantir que todas as configurações sejam corretamente carregadas: `conda init`

    Isso deve garantir que o `Conda` esteja configurado corretamente para o seu ambiente de _shell_.

5. Fechar e abrir o `Terminal Emulator`

6. **Ative o ambiente base do `Conda`**: Verificar se a palavra `(base)` aparece no seu `Terminal Emulator`. Se estiver aparecendo, tudo está configurado corretamente, se não, tente ativar o ambiente `base` do `Conda` novamente após as configurações: `conda activate base`

    Se tudo estiver configurado corretamente, você não deve ver mais o erro `CondaError: Run 'conda init' before 'conda activate'`.

6. **Verifique se o `Conda` está funcionando**: Após ativar o ambiente `base`, você pode verificar se o `Conda` está funcionando corretamente executando comandos como `conda list` para listar os pacotes instalados.

**Observações adicionais**:

- Certifique-se de que não há linhas no seu arquivo de inicialização do _shell_ que possam interferir com a configuração do Conda, especialmente se você estiver usando gerenciadores de ambiente como virtualenv.

- Se estiver usando o `Zsh` com `Oh My Zsh`, pode ser necessário ajustar algumas configurações adicionais para integrar o Conda corretamente.

Seguindo esses passos, você deve ser capaz de configurar e usar o Conda corretamente no seu ambiente de desenvolvimento.


### 2.2 Acelerar o pacote `scikit-learn`

O pacote instalado do `scikit-learn` pode ser acelerado usando o `scikit-learn-intelex`.
Mais detalhes estão disponíveis aqui: https://intel.github.io/scikit-learn-intelex

```
Installed package of scikit-learn can be accelerated using scikit-learn-intelex.
More details are available here: https://intel.github.io/scikit-learn-intelex

For example:

$ conda install scikit-learn-intelex
$ python -m sklearnex my_application.py
```

1. Execute a primeira linha acima para acelerar o pacote `scikit-learn`.

### 2.3 Atualizar todos os pacotes do `conda`

Para atualizar todos os pacotes do `conda`, siga o(s) passo(s) abaixo:

1. Depois da instalação, execute o comando: `conda update --all`

## 3. Configurar o ambiente virtual `base` para ser o `Python 3.8` no `Anaconda3`

Para verificar se você tem o `Anaconda` instalado no seu computador e, especificamente, se é uma versão que inclui o `Python 3.8`, você pode seguir estes passos:

1. **Verificar a versão do `Anaconda`:** Abra um `Terminal Emulator` e digite o seguinte comando: `conda --version`

    Este comando retornará a versão do conda instalada, se o `Anaconda` ou `Miniconda` estiver instalado no seu sistema.

2. **Verificar a lista de ambientes do `Conda`:** Para ver uma lista de todos os ambientes do conda criados, que podem incluir um ambiente com o `Python 3.8`, use: `conda env list`

Para definir o `Python 3.8` como a versão do `Python` no ambiente `base` do seu `Anaconda`, você precisará atualizar o `Python` nesse ambiente. Este processo substituirá a versão atual do `Python` (`3.11.5`, por exemplo) pela versão `3.8` no ambiente `base`. Aqui está como você pode fazer isso:

3. **Abra um `Terminal Emulator`:** Certifique-se de que você está no ambiente `base` do `Anaconda`. Se não estiver, você pode ativar o ambiente `base` com o comando: `conda activate base`

4. **Atualizar o `Python` para a versão `3.x`:** Use o comando `conda install` para especificar a versão do `Python` que deseja instalar no ambiente `base`. Execute o seguinte comando: `conda install python=3.x`

    Substitua o `x` pela versão desejada, por exemplo: `conda install python=3.8`

    Esse comando solicitará que o `Conda` atualize o `Python` e possivelmente alguns pacotes dependentes para garantir compatibilidade com o `Python 3.x`. Siga as instruções na tela para confirmar a instalação.

3. **Verificar a versão do `Python`:** Após a conclusão da instalação, verifique a versão do `Python` para garantir que a atualização foi bem-sucedida: `python --version`

    A saída deve mostrar `Python 3.8.x`, confirmando que o ambiente `base` agora está usando o `Python 3.8`.

## 4. Desinstalar o `Anaconda`

Para desinstalar o `Anaconda` do seu sistema, siga estes passos:

### 4.1 Remover a instalação do `Anaconda`**

1. Remova o diretório de instalação:

    - Primeiro, você deve remover o diretório onde o `Anaconda` foi instalado. Se o `Anaconda` foi instalado no diretório padrão `/home/<username>/anaconda3`, você pode remover o diretório com o seguinte comando: `rm -rf ~/anaconda3`

    - Caso o `Anaconda` tenha sido instalado em outro diretório, substitua `~/anaconda3` pelo caminho correto.

2. **Remova os arquivos de configuração do `Conda`**: Em alguns casos, podem existir arquivos de configuração em seu diretório `home` que você pode querer remover. Execute os seguintes comandos para remover esses arquivos: `rm -rf ~/.condarc ~/.conda ~/.continuum`


### 4.2 Remover referências no arquivo de perfil

1. **Edite o arquivo de perfil**:

    1.1 Abra o arquivo de perfil global (para uma instalação global) ou o arquivo de perfil do usuário (por exemplo, `~/.bashrc`, `~/.zshrc` etc.), dependendo de onde você adicionou o caminho do `Anaconda`.

    1.2 **Para editar o arquivo `~/.bashrc` ou `~/.zshrc`**:

    `sudo nano ~/.bashrc`

    ou
    
    `nano ~/.zshrc`

2. **Remova as linhas relacionadas ao `Anaconda`**:

    2.1 Localize e remova qualquer linha que tenha sido adicionada para configurar o `PATH` para o `Anaconda`, como: `export PATH="$HOME/anaconda3/bin:$PATH"`

    2.2 Salve as alterações e saia do editor (`Ctrl+O` para salvar e `Ctrl+X` para sair no `Nano`).

3. **Recarregue o arquivo de perfil**: Após remover as linhas, recarregue o arquivo de perfil para aplicar as mudanças:

    `source ~/.bashrc`

    ou

    `source ~/.zshrc`

### 4.3 Verificar a remoção

1. **Verifique se o `Anaconda` foi removido**:

    1.1 Tente executar o comando `conda` para verificar se ainda está disponível: `conda`

    1.2 Se o comando não for encontrado, isso indica que o `Anaconda` foi removido com sucesso.


### 4.4 Remover dependências adicionais (opcional)

Se você instalou pacotes ou aplicativos adicionais relacionados ao `Anaconda`, você pode querer removê-los também. Certifique-se de verificar se há outras dependências ou arquivos associados ao `Anaconda` que possam precisar de limpeza adicional.

Seguindo estes passos, você deverá conseguir desinstalar o `Anaconda` do seu sistema de forma completa.


## Referências

[1] OPENAI. ***Instalar arquivo .sh no ubuntu.*** Disponível em: <https://chat.openai.com/c/073320a8-7cc5-4590-9da0-d2bcc7093c88> (texto adaptado). Acessado em: 17/10/2023 16:31.

[2] OPENAI. ***VS code: editor popular.*** Disponível em: <https://chat.openai.com/c/b640a25d-f8e3-4922-8a3b-ed74a2657e42> (texto adaptado). Acessado em: 14/11/2023 09:33.

