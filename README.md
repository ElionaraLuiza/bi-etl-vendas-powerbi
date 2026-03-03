# bi-etl-vendas-powerbi
Fluxo completo de ETL aplicado a dados de vendas com modelagem estrela e dashboard em Power BI.
# BI ETL - Análise de Vendas com Power BI

## 🎯 Objetivo
Construir um fluxo completo de ETL (Extração, Transformação e Carga) utilizando dados de vendas, aplicando modelagem de dados e criação de métricas em DAX no Power BI.

## 📊 Contexto
Projeto desenvolvido com base em dados de vendas para simular o processo real de um analista de BI, desde o tratamento dos dados até a criação de dashboard.

## 🔄 Processo de ETL
- Extração de dados a partir de arquivo Excel/CSV, PDF e TXT
- Tratamento no Power Query
- Ajuste de tipos de dados
- Criação de colunas auxiliares
- Modelagem no formato estrela
- Criação de medidas DAX

## 🛠 Ferramentas utilizadas
- Power BI
- Power Query
- DAX
- GitHub

---

## 🔄 Transformações no Power Query

Nesta etapa foram realizadas as transformações necessárias para limpar, padronizar e preparar as tabelas antes da modelagem de dados.

### 📦 Fornecedores – Tabela Auxiliar

- Remoção de colunas desnecessárias (`Data` e `Usuário`);
- Mescla de consulta trazendo a **origem do fornecedor** para a tabela;
- Desabilitação da carga desta tabela no modelo, mantendo-a apenas como apoio no Power Query.

### 📦 Produtos – Tabela Dimensão

- Preenchimento de células nulas em campos importantes;
- Mescla de consulta trazendo **nome do fornecedor** e **origem** a partir da tabela Fornecedores;
- Uso da tabela de Fornecedores como base para enriquecer os dados de produtos.

### 📦 Origem Fornecedor – Tabela Auxiliar

- Definição de cabeçalho;
- Transformação de colunas em linhas (unpivot);
- Renomeação de colunas;
- Exclusão de linhas em branco;
- Substituição de valores;
- Desabilitação da carga no modelo, mantendo apenas como etapa intermediária de transformação.

### 📦 Lojas – Tabela Dimensão

- Remoção de linhas inválidas;
- Exclusão de colunas desnecessárias;
- Definição de cabeçalho;
- Padronização geral de formato;
- Alteração de tipos de dados (texto, número, data);
- Criação da coluna **Região**;
- Ajustes de texto (corte de espaços à esquerda e à direita).

### 📦 Metas – Tabela Fato

- Definição de cabeçalho;
- Remoção de valores nulos irrelevantes;
- Transformação de colunas em linhas (unpivot) para normalizar a estrutura;
- Remoção de linhas com totais;
- Ajuste de tipos de dados para permitir cálculos corretamente.

### 📦 Pedidos – Tabela Fato

- Carga de arquivos por pasta (vários arquivos de pedidos unificados em uma única tabela);
- Unificação de tabelas de pedidos;
- Acerto da coluna de nome do arquivo;
- Mescla de coluna de datas, quando necessário;
- Alteração de tipos de dados;
- Criação de colunas de apoio (por exemplo: Mês/Ano, Faixa de preço, Tipo de venda).

---

### 🧩 Conceitos Utilizados

- **Tabela Fato:** concentra eventos/ transações e números que variam (como pedidos e metas), registrando o que aconteceu.
- **Tabela Dimensão:** traz descrições e contexto (clientes, produtos, lojas, tempo), usada para detalhar as análises.
- **Tabela Auxiliar:** usada como etapa intermediária de transformação no Power Query, ajudando a organizar/normalizar os dados; geralmente fica com a carga desabilitada no modelo final.

Projeto desenvolvido como parte do meu portfólio de Business Intelligence.
