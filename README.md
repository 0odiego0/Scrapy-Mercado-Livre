# Scrapy - Mercado Livre: Coleta de Dados de Notebooks

Este projeto utiliza o framework [Scrapy](https://scrapy.org/) para realizar **web scraping de notebooks no site do Mercado Livre**. Ele coleta informações de produtos como marca, nome, vendedor, avaliações e preços.

## Objetivo

Extrair dados estruturados de notebooks listados no Mercado Livre para fins de:

- Análise de mercado
- Comparação de preços
- Estudos de dados e visualizações

---

## 🚀 Tecnologias utilizadas

- Python 3.10+
- Scrapy
- Git (para versionamento)
- GitHub (armazenamento do projeto)

---

## Estrutura do projeto

scrapy_mercado_livre/
└── coleta/
├── coleta/
│ ├── spiders/
│ │ └── notebook_spider.py # Spider principal
│ ├── init.py
│ └── settings.py
├── scrapy.cfg
└── README.md


---

##Dados coletados

Para cada produto encontrado, o spider extrai:

- **Marca** (`brand`)
- **Nome** (`name`)
- **Vendedor** (`seller`)
- **Avaliação média** (`reviews_rating_number`)
- **Quantidade de avaliações** (`reviews_amount`)
- **Preço antigo** (`old_money`)
- **Preço atual** (`new_money`)

---

## Paginação

O spider acessa várias páginas (até 10 por padrão), simulando a navegação paginada via offset da URL.

---

## Como executar

Crie e ative um ambiente virtual (opcional, mas recomendado):

python -m venv .venv
source .venv/bin/activate  # Linux/macOS
.venv\Scripts\activate     # Windows

    Instale as dependências:

pip install scrapy

    Execute o spider:

scrapy crawl notebook -o notebooks.json

Isso irá gerar um arquivo notebooks.json com os dados extraídos.

OBS: Você também pode gerar o arquivo em csv se preferir, basta apenas trocar o "notebooks.json" por notebooks.csv.
