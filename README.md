# BI ETL - Análise de Vendas com Power BI

## 🎯 Objetivo
Construir um fluxo completo de ETL (Extração, Transformação e Carga) utilizando dados de vendas, aplicando modelagem de dados em formato estrela e criação de métricas em DAX no Power BI.

## 📊 Contexto
Projeto desenvolvido com base em dados de vendas para simular o processo real de um Analista de BI, desde o tratamento das bases até a modelagem e futura construção de dashboard.

---

## 🔄 Processo de ETL

- Extração de dados a partir de arquivos Excel, CSV, PDF e TXT  
- Tratamento e transformação no Power Query  
- Ajuste e padronização de tipos de dados  
- Criação de colunas auxiliares  
- Organização das tabelas em modelo estrela  
- Preparação para criação de medidas em DAX  

---

## 🔧 Transformações no Power Query

Nesta etapa foram realizadas transformações para limpar, padronizar e preparar as tabelas antes da modelagem de dados.

### 📦 Fornecedores – Tabela Auxiliar

- Remoção de colunas desnecessárias (Data e Usuário);
- Mescla de consulta trazendo a origem do fornecedor;
- Desabilitação da carga da tabela no modelo final.

### 📦 Produtos – Tabela Dimensão

- Preenchimento de células nulas;
- Mescla de consulta trazendo nome e origem do fornecedor;
- Enriquecimento da base utilizando a tabela Fornecedores.

### 📦 Origem Fornecedor – Tabela Auxiliar

- Definição de cabeçalho;
- Transformação de colunas em linhas (Unpivot);
- Renomeação de colunas;
- Exclusão de linhas em branco;
- Substituição de valores;
- Desabilitação de carga no modelo.

### 📦 Lojas – Tabela Dimensão

- Remoção de linhas inválidas;
- Exclusão de colunas desnecessárias;
- Definição de cabeçalho;
- Padronização de formato;
- Alteração de tipos de dados (texto, número e data);
- Criação da coluna Região;
- Ajustes de texto (remoção de espaços à esquerda e direita).

### 📦 Metas – Tabela Fato

- Definição de cabeçalho;
- Remoção de valores nulos irrelevantes;
- Transformação de colunas em linhas (Unpivot);
- Remoção de linhas de total;
- Ajuste de tipos de dados para permitir cálculos corretos.

### 📦 Pedidos – Tabela Fato

- Carga de arquivos por pasta (unificação de múltiplos arquivos);
- Consolidação das tabelas de pedidos;
- Ajuste da coluna de nome do arquivo;
- Tratamento de coluna de datas;
- Alteração de tipos de dados;
- Criação de colunas auxiliares (Mês/Ano, Faixa de Preço, Tipo de Venda).

---

## 🧩 Conceitos Utilizados

- **Tabela Fato:** concentra eventos/transações e métricas numéricas que variam (como pedidos e metas).
- **Tabela Dimensão:** fornece contexto descritivo (produtos, lojas, tempo) para análise dos dados.
- **Tabela Auxiliar:** utilizada como etapa intermediária de transformação no Power Query, geralmente com carga desabilitada no modelo final.

---

## 🛠 Ferramentas Utilizadas

- Power BI  
- Power Query  
- DAX  
- GitHub  

---

Projeto desenvolvido como parte do meu portfólio em Business Intelligence.
