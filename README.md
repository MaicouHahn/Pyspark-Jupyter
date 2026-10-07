# Trabalho de Pesquisa: Apache Spark com Delta Lake e Apache Iceberg

Este é o repositório do projeto de pesquisa e implementação prática envolvendo Apache Spark, Delta Lake e Apache Iceberg. O ambiente de desenvolvimento foi homologado para execução em terminais Ubuntu (WSL) no Windows, utilizando o Visual Studio Code e o gerenciador de pacotes UV.

## Integrantes do Grupo

* Maicou Hahn Fortuna - \[[Contato/GitHub](https://github.com/MaicouHahn)\]

* Guilherme Victor Machado - \[[Contato/GitHub](https://github.com/gvm7b)\]

* Evandro Luiz Rodrigues Damazio - \[Contato/GitHub\]

## Documentação (MKDOCS)

A contextualização teórica do trabalho, bem como as explicações sobre Apache Spark, Iceberg e Delta Lake, estão disponíveis no nosso site estático.

* **Acesse a documentação completa aqui:** \[INSERIR_URL_PUBLICA_GH_PAGES\]

## Instalação e Configuração do Ambiente (Ubuntu / WSL)

O passo a passo a seguir descreve como preparar o sistema do zero para rodar o projeto.

### 1. Instalar Dependências e o Pyenv

Atualize os pacotes do sistema e instale as dependências necessárias para a compilação do Python:

```
sudo apt update
sudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev curl git \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev libzstd-dev

```

Adicione o Pyenv ao PATH do seu sistema executando os comandos abaixo:

```
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init - bash)"' >> ~/.bashrc
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc

```

Rode o instalador do Pyenv e atualize o terminal:

```
curl -fsSL https://pyenv.run | bash
~/.pyenv/bin/pyenv init --install
source ~/.bashrc

```

Confirme se a instalação foi bem-sucedida verificando a versão:

```
pyenv --version

```

### 2. Instalar e Configurar o Python 3.11.9

Instale a versão padrão do projeto e defina-a como global para todo o sistema:

```
pyenv install 3.11.9
pyenv global 3.11.9

```

*Dica: Confirme rodando `pyenv versions`. A versão 3.11.9 deve aparecer com um asterisco (*) ao lado indicando que é a versão global ativa.\*

### 3. Instalar Pipx e UV

O Pipx será utilizado para instalar o UV de forma isolada, evitando conflitos com o Pyenv.

```
# Confirme a versão do Python em uso (deve ser a 3.11.9)
python --version

# Instale o pipx e garanta que ele está no PATH
pip install pipx
pipx ensurepath

# Instale o gerenciador de pacotes UV
pipx install uv

```

*Nota: Valide a instalação rodando `pipx list`. Nunca utilize `pip install uv` diretamente para não instalar os gerenciadores globais fora do escopo do Pipx.*

## Clonagem e Configuração do Ambiente Único do Projeto

Seguindo as diretrizes do projeto, utilizamos **um único ambiente** para executar tanto o Delta Lake quanto o Apache Iceberg.

### 1. Clonar o Repositório

Faça o clone do repositório principal e entre na pasta:

```
git clone https://github.com/MaicouHahn/Pyspark-Jupyter.git
cd Pyspark-Jupyter

```

### 2. Configurar o Ambiente Único (UV)

Na raiz do projeto, inicie o UV, ative o ambiente virtual e adicione todas as dependências necessárias de uma só vez:

```
uv init
uv venv
source .venv/bin/activate
uv add pyspark==3.5.3 delta-spark==3.2.0 jupyterlab ipykernel

```

*Nota: Ao usar o comando `source .venv/bin/activate`, o ambiente virtual será ativado e o caminho no seu terminal ficará entre parênteses, ex: `(Pyspark-Jupyter) maicou@Maicou:~/Pyspark-Jupyter$`. Para sair dele posteriormente, basta digitar `deactivate`.*

## Abrindo o Projeto no Visual Studio Code

Agora que o ambiente único está configurado, você pode utilizar o VS Code (ou o Jupyter Lab diretamente no navegador) para executar os notebooks.

1. Abra o VS Code pelo Windows e abra a pasta raiz do projeto (`Pyspark-Jupyter`).

2. No canto inferior esquerdo do editor, clique e selecione o ambiente de conexão **Ubuntu (WSL)**.

3. Caso surja um alerta de segurança, marque a pasta como **"Trusted"** (Confiável).

4. Abra qualquer um dos seus notebooks (`.ipynb`).

5. No canto superior direito da interface do notebook, clique em **Select Kernel** (Selecionar Kernel) e escolha o **Python Environment** correspondente ao ambiente virtual criado (versão `3.11.9` localizada na pasta `.venv` do projeto).

## Bibliotecas e Versões Principais

* Python: `^3.11.9`

* PySpark: `^x.x.x`

* JupyterLab: `^x.x.x`

* Delta-Spark: `^x.x.x`
