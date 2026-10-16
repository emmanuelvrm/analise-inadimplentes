# Análise de Inadimplentes

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/emmanuelvrm/analise-inadimplentes/blob/main/notebooks/Analise_Inadimplentes.ipynb)
![Python](https://img.shields.io/badge/Python-3.10+-blue) ![License](https://img.shields.io/badge/license-MIT-green)

Análise exploratória de dados de clientes de uma instituição financeira para entender **por que um cliente deixa de honrar suas dívidas**, a partir de atributos como salário, escolaridade e movimentação financeira.

## Contexto

O dataset a ser analisado contém informações sobre clientes de uma instituição financeira. Em especial, estamos interessados em explicar a segunda coluna, chamada de default, que indica se um cliente é adimplente(default = 0), ou inadimplente (default = 1), ou seja, queremos entender o porque um cliente deixa de honrar com suas dívidas baseado no comportamento de outros atributos, como salário, escolaridade e movimentação financeira.

Abaixo uma descrição completa deste atributos:

| Coluna  | Descrição |
| ------- | --------- |
| id      | Número da conta |
| default | Indica se o cliente é adimplente (0) ou inadimplente (1) |
| idade   | Idade do cliente, em anos |
| sexo    | Sexo do cliente |
| dependentes | Quantidade de dependentes |
| escolaridade | Nível de escolaridade do cliente |
| estado_civil | Estado civil do cliente |
| salario_anual | Faixa do salario mensal multiplicado por 12 |
| tipo_cartao | Categoria do cartao: blue, silver, gold e platinium |
| meses_de_relacionamento | Quantidade de meses desde a abertura da conta |
| qtd_produtos | Quantidade de produtos contratados |
| iteracoes_12m | Quantidade de iteracoes com o cliente no último ano |
| meses_inatico_12m | Quantidade de meses que o cliente ficou inativo no último ano |
| limite_credito | Valor do limite do cartão de crédito |
| valor_transacoes_12m | Soma total do valor das transações no cartão de crédito no último ano |
| qtd_transacoes_12m | Quantidade total de transações no cartão de crédito no último ano |

> Observação: na tabela, o nome das colunas segue exatamente o que está no arquivo `data/credito.csv`.

## O que foi feito

1. Descrição e exploração dos dados (tipos, valores faltantes, estatísticas descritivas).
2. Transformação e limpeza: comparação entre **preencher faltantes com a moda** e **remover as linhas com faltantes** (testes Qui-Quadrado e proporções). A remoção afetou menos as variáveis categóricas e foi a abordagem adotada.
3. Visualização dos dados.
4. Análise univariada e bivariada (adimplentes × inadimplentes), incluindo mapas de correlação.

## Principais conclusões

- A maioria dos clientes é **adimplente**.
- Adimplentes tendem a ter mais produtos contratados, maior valor e quantidade de transações e maior limite de crédito.
- Inadimplentes tendem a ter mais interações com a instituição e mais meses de inatividade.
- Há forte correlação positiva entre valor e quantidade de transações, e entre idade e tempo de relacionamento.
- As diferenças entre os grupos existem, mas **não são marcantes o bastante para explicar a inadimplência apenas com essas variáveis**, o que aponta para a necessidade de mais atributos ou de modelagem preditiva.

## Estrutura do repositório

```
analise-inadimplentes/
├── data/
│   └── credito.csv
├── notebooks/
│   └── Analise_Inadimplentes.ipynb
├── requirements.txt
└── README.md
```

## Como executar

```bash
git clone https://github.com/emmanuelvrm/analise-inadimplentes.git
cd analise-inadimplentes
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/Analise_Inadimplentes.ipynb
```

Ou abra direto no Google Colab pelo botão no topo (o notebook baixa o CSV do GitHub automaticamente).

## Licença

Código e notebooks sob licença MIT (veja `LICENSE`).
