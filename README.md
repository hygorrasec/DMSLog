## INSTALANDO QUALQUER VERSÃO DO JAVA:

### a) Baixar o java mais recente:

https://www.oracle.com/java/technologies/downloads
	
### b) Criar uma pasta no diretório /home chamado "apps", depois descompactar o java baixado dentro desse diretório (sugiro renomear a pasta para jdk_x, onde x é a versão baixada).
	
### c) Adicionar no final do arquivo .bashrc que está no diretório /home (Ctrl + H pra mostrar os arquivos e pastas ocultas):

```
# Configuração Java
JAVA_HOME=/home/NOME_DO_USUARIO/apps/jdk_18
export JAVA_HOME

PATH=$PATH:$JAVA_HOME/bin
export PATH
```

### d) Abra um novo terminal e confira se o java foi instalado corretamente.

```
java --version
```

## INSTALANDO QUALQUER VERSÃO DO PYTHON:

### a) Atualizar o Sistema:

```
sudo apt-get update
```

### b) Instalar as dependências:

```
sudo apt install build-essential zlib1g-dev libjpeg-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev sqlite3 liblzma-dev curl libbz2-dev
```

### c) Baixar o Python mais recente e descompactar:
	
https://www.python.org/downloads

### d) Com o terminal aberto no diretório do python baixado, executar os comandos um de cada vez:

```
./configure --enable-optimizations --with-ensurepip=install
make -j 2
sudo make altinstall
```

### e) Verifique se foi instalado corretamente:

```
python3.x --version
pip3.x --version
```

### f) Atualizar o pip:

```
sudo pip3.x install --upgrade pip
```

## FERRAMENTAS PARA AMBIENTE VIRTUAL

### a) Instalar o Virtualenv:

```
sudo pip3.x install virtualenv virtualenvwrapper
```

### b) Configurar um diretório padrão para o virtualenv. Adicionar no final do arquivo .bashrc que está no diretório /home (Ctrl + H pra mostrar os arquivos e pastas ocultas):

```
# Virtualenv
export WORKON_HOME=$HOME/.virtualenvs

export VIRTUALENVWRAPPER_PYTHON=/usr/local/bin/python3.10
# Observação acima. Para identificar o diretório do Python, digite no terminar: which python3.x (ontem x é a versão do seu Python instalado)

source /usr/local/bin/virtualenvwrapper.sh
```

### c) Abra um novo terminal e crie um novo ambiente virtual:

```
mkvirtualenv NOME_DO_AMBIENTE_VIRTUAL
```

### d) Se tudo deu certo, você estará conectado ao ambiente virtual que foi criado. Para sair, digite o comando abaixo:

```
deactivate
```

### e) Para acessar novamente o ambiente virtual que você criou, digite o comando abaixo:

```
workon NNOME_DO_AMBIENTE_VIRTUAL
```

### f) Para remover um ambiente virtual, digite o comando abaixo:

```
rmvirtualenv NOME_DO_AMBIENTE_VIRTUAL
```

## CRIANDO TOKEN DE ACESSO PESSOAL NO GITHUB:

### a) Na sua conta do GitHub, vá em Setting => Developer settings => Personal access tokens => Generate new token => Preencha o formulário => clique em Generate token => Copie o Token gerado. O TOKEN será algo como:
```ghp_sFhFsSHhTzMDreGRLjmks4Tzuzgthdvfsrta```

### b) No terminal digite (altere com seus dados):

```
git remote set-url origin https://TOKEN@github.com/YOUR-USERNAME/REPOSITORY
```

### c) Para Linux, você precisa configurar o cliente Git local com um nome de usuário e endereço de e-mail:

```
git config --global user.name "your_github_username"
git config --global user.email "your_github_email"
```

### d) Depois que o Git estiver configurado, podemos começar a usá-lo para acessar o GitHub.
