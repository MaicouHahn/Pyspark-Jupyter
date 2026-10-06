# Trabalho de Pesquisa: Apache Spark com Delta Lake e Apache Iceberg

Este é o repositório público do projeto de pesquisa e implementação prática envolvendo Apache Spark, Delta Lake e Apache Iceberg.

O objetivo deste projeto é demonstrar a configuração de um ambiente único executando PySpark e Jupyter Labs, além de evidenciar operações de manipulação de dados (INSERT, UPDATE e DELETE) em tabelas Delta e Iceberg.

##  Integrantes do Grupo

* Maicou Hahn Fortuna - \[[Contato/GitHub](https://github.com/MaicouHahn)\]

* Guilherme Victor Machado - \[[Contato/GitHub](https://github.com/gvm7b)\]

* Aluno 3 - \[Contato/GitHub\]

## Documentação (MKDOCS)

A contextualização teórica do trabalho está disponível no nosso repositório construído com o MKDOCS.

* **Acesse a documentação completa aqui:** 

## Pré-requisitos e Ferramentas

Para reproduzir este ambiente, você precisará das seguintes ferramentas:

* **Java 11 ou 17** (Requisito obrigatório para rodar o Apache Spark localmente).

* **Python 3.9+**

* **UV** (Gerenciador de pacotes e projetos Python ultrarrápido escolhido para este projeto).

*Referências de estudo para o ambiente foram baseadas no canal DataWay BR e nos repositórios github.com/jlsilva01/spark-delta e github.com/jlsilva01/spark-iceberg.*

## Passo a Passo para Reproduzir o Ambiente

Siga as instruções abaixo para clonar e rodar o projeto na sua máquina local com o UV:

### 1. Clonar o Repositório

Faça o clone deste repositório público em seu computador:

```
git clone https://github.com/MaicouHahn/Pyspark-Jupyter.git
cd Pyspark-Jupyter

```

### 2. Instalar o UV

Caso não tenha o UV instalado, você pode instalá-lo via pip:

```
pip install uv

```

### 3. Criar e Ativar o Ambiente Virtual

O UV gerencia ambientes virtuais de forma muito eficiente. Crie e ative o ambiente com os comandos abaixo:

```
# Cria o ambiente virtual (.venv)
uv venv

# Ativa o ambiente no Windows:
.venv\Scripts\activate

# Ativa o ambiente no Linux/MacOS:
source .venv/bin/activate

```

### 4. Instalar as Dependências do Projeto

Com o ambiente ativado, instale as bibliotecas necessárias (PySpark, Jupyter Labs, Delta Spark, etc). Sincronize o ambiente utilizando o arquivo de configuração do projeto:

```
uv sync

```

*(Nota: Certifique-se de que o arquivo `pyproject.toml` está presente na raiz do diretório).*

### 5. Executar o Jupyter Labs

Para abrir o ambiente de desenvolvimento unificado, inicie o Jupyter Labs (ou utilize a extensão do Jupyter no Visual Studio Code):

```
jupyter lab

```

## Estrutura do Projeto

O repositório está organizado da seguinte forma, utilizando o padrão de projetos Python para Engenharia de Dados:

* `delta_lake.ipynb`: Arquivo de notebook implementando o cenário e códigos em Delta Lake.

* `apache_iceberg.ipynb`: Arquivo de notebook implementando o cenário e códigos em Apache Iceberg.

* `cenario_dados.ipynb`: Notebook contendo a descrição do cenário da(s) tabela(s), modelo ER, imagens, códigos DDL e exemplos de operações INSERT, UPDATE e DELETE.

* `pyproject.toml`: Arquivo de configuração e gerenciamento de dependências do projeto (UV).

* `/mkdocs`: Diretório contendo os arquivos fonte para as páginas web de explicação teórica.

## Bibliotecas e Versões Principais

* Python: `^3.11.9`

* PySpark: `^x.x.x`

* JupyterLab: `^x.x.x`

* Delta-Spark: `^x.x.x`
