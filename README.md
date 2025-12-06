# 🏥 Análise e Predição de Cancelamento de Planos de Saúde

Este projeto de Ciência de Dados investiga o ciclo de vida dos planos de saúde no Brasil, utilizando dados da ANS (Agência Nacional de Saúde Suplementar). O objetivo é identificar padrões que levam à inatividade dos planos e desenvolver um modelo preditivo para estimar o risco de cancelamento.

**Disciplina:** Ciência de Dados: Análise de Dados Aplicada (UTFPR)
**Prof.:** Dr. Eduardo Pena
**Autores:** Thiago Ramos Velozo, Christopher Eduardo Zai

---

## 🎯 Objetivo do Projeto

Responder à pergunta: **Quais características contratuais e da operadora mais influenciam o cancelamento de um plano de saúde?**

Testamos três hipóteses principais:
1.  **Tempo de Vida (H1):** Planos mais antigos são mais estáveis.
2.  **Características do Produto (H2):** Planos "Municipais" e "Coletivos por Adesão" têm maior risco de cancelamento.
3.  **Modelagem (H3):** Modelos baseados em árvores (Random Forest) superam modelos lineares (Regressão Logística) na predição.

---

## 🗂 Estrutura do Repositório

O projeto foi desenvolvido em etapas incrementais. Abaixo está o conteúdo de cada diretório:

### [Etapa 1: Planejamento](./Etapa_1)
* Definição do problema, escolha do dataset e elaboração das hipóteses.
* 📄 *Arquivo principal:* `EntregaParcial1.pdf`

### [Etapa 2 e 3: Limpeza, EDA e SQL](./Etapa_2_3)
* **Limpeza:** Tratamento de nulos, padronização de datas e filtro da variável alvo (`Ativo` vs `Cancelado`).
* **Feature Engineering:** Criação da variável `IDADE_PLANO_DIAS`.
* **Análise Exploratória:** Teste visual das hipóteses H1 e H2.
* **SQL:** Consultas analíticas utilizando **DuckDB** para agregação de dados.
* 📓 *Notebook:* `Pena_tência.ipynb`

### [Etapa 4: Modelagem Preditiva (Atual)](./Etapa_4)
* Treinamento e validação de modelos de Machine Learning.
* **Modelos Testados:** Regressão Logística (Baseline) vs. Random Forest.
* **Resultados:** Random Forest obteve melhor performance (F1-Score: **0.87**), confirmando a hipótese H3.
* 📓 *Notebook Principal:* `predicao-notebook-3.ipynb`
* 💾 *Dataset Processado:* `planos_saude_limpo.parquet`

---

## 🛠 Tecnologias Utilizadas

* **Linguagem:** Python 3.10+
* **Manipulação de Dados:** Pandas, DuckDB
* **Visualização:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-learn (Logistic Regression, Random Forest, Metrics)
* **Formato de Dados:** Parquet (para performance e persistência de tipos)

---

## 🚀 Como Executar o Projeto

Para reproduzir os resultados da **Etapa 4 (Modelagem)**, siga os passos abaixo:

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/ttrrv/cdpf.git](https://github.com/ttrrv/cdpf.git)
    cd cdpf/Etapa_4
    ```

2.  **Instale as dependências:**
    ```bash
    pip install pandas duckdb matplotlib seaborn scikit-learn pyarrow
    ```

3.  **Execute o Notebook:**
    Abra o arquivo `predicao-notebook-3.ipynb` no Jupyter Notebook, Google Colab ou VS Code.
    > **Nota:** Certifique-se de que o arquivo `planos_saude_limpo.parquet` está na mesma pasta do notebook para que o carregamento dos dados funcione corretamente.

---

## 📊 Resultados Principais

* **Fatores de Risco:** A análise confirmou que a abrangência "Grupo de Municípios" e planos "Coletivos por Adesão" possuem taxas de cancelamento significativamente maiores.
* **Performance do Modelo:** O modelo Random Forest conseguiu capturar a não-linearidade dos dados, superando a Regressão Logística, especialmente na identificação de planos cancelados (Recall).

---

## 📞 Contato

Caso tenha dúvidas sobre a execução ou os dados:
* [Link para o repositório](https://github.com/ttrrv/cdpf)
