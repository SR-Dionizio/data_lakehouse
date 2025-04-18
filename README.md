# Data Lakehouse

Este projeto implementa uma arquitetura moderna de Data Lakehouse, combinando as melhores características de Data Lakes e Data Warehouses. O projeto utiliza tecnologias modernas para processamento, transformação e visualização de dados.

## Tecnologias Utilizadas

- **Python 3.10+**
- **Taipy**: Framework para desenvolvimento de aplicações web e dashboards
- **DBT (Data Build Tool)**: Ferramenta para transformação de dados
- **DuckDB**: Banco de dados analítico
- **Polars**: Biblioteca para processamento de dados em memória
- **PostgreSQL**: Banco de dados relacional
- **Terraform**: Infraestrutura como código
- **UV**: Gerenciador de pacotes Python moderno e rápido

## Estrutura do Projeto

```
.
├── frontend/               # Interface do usuário
│   ├── dashboard/         # Componentes do dashboard
│   └── main.py           # Aplicação principal Taipy
├── dbt_lakehouse/         # Transformações DBT
│   ├── models/           # Modelos de dados
│   ├── analyses/         # Análises ad-hoc
│   ├── macros/           # Macros reutilizáveis
│   ├── seeds/            # Dados iniciais
│   ├── snapshots/        # Capturas de estado dos dados
│   └── tests/            # Testes de dados
├── terraform/             # Configurações de infraestrutura
├── generate_datasets/     # Scripts para geração de dados
├── datasets/              # Dados brutos e processados
└── logs/                  # Logs da aplicação
```

## Configuração do Ambiente

1. Clone o repositório
2. Crie um ambiente virtual Python:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # Linux/Mac
   # ou
   .venv\Scripts\activate     # Windows
   ```
3. Instale as dependências usando UV:
   ```bash
   uv pip install -e .
   ```
4. Configure as variáveis de ambiente no arquivo `.env`

## Gerenciamento de Dependências com UV

O projeto utiliza UV como gerenciador de pacotes Python, oferecendo:
- Instalação rápida de pacotes
- Resolução de dependências otimizada
- Gerenciamento de ambiente virtual integrado
- Cache de pacotes eficiente

O arquivo `uv.lock` mantém o registro das versões exatas das dependências para garantir reprodutibilidade.

## Pipeline de Dados com DBT

O projeto utiliza DBT (Data Build Tool) para transformação de dados, com a seguinte estrutura:

### Estrutura DBT
- **models/**: Contém os modelos SQL para transformação de dados
- **analyses/**: Queries SQL para análises ad-hoc
- **macros/**: Funções SQL reutilizáveis
- **seeds/**: Arquivos CSV para dados de referência
- **snapshots/**: Capturas de estado dos dados para histórico
- **tests/**: Testes de qualidade dos dados

### Comandos DBT Principais
```bash
# Executar todos os modelos
dbt run

# Executar testes
dbt test

# Gerar documentação
dbt docs generate

# Visualizar documentação
dbt docs serve
```

## Dashboard

O projeto inclui um dashboard interativo construído com Taipy, que pode ser iniciado com:

```bash
python frontend/main.py
```

O dashboard estará disponível em `http://localhost:5000`

## Infraestrutura

A infraestrutura do projeto é gerenciada através do Terraform, com as configurações localizadas no diretório `terraform/`. 

## Dependências Principais

- taipy v3.1.1
- polars v1.8.2
- duckdb v1.1.1
- dbt-core v1.8.7
- dbt-postgres v1.8.2
- matplotlib v3.9.2
- seaborn v0.13.2
- plotly v5.24.1

