# Projeto de Consultoria: Otimização do Sucesso de Alunos (Walsoft)

**Autor:** Guilherme Bertanha Constante | **GitHub:** https://github.com/guibertanha/data-science-study

---

## 1. Contexto e Objetivo do Projeto

Este projeto simula uma consultoria em Ciência de Dados para o "Walsoft Computer Institute". O objetivo é analisar um dataset de alunos para fornecer recomendações estratégicas que melhorem os resultados do programa de Business Intelligence da instituição, focando em otimização de admissões e identificação de fatores de sucesso.

## 2. Limpeza e Pré-processamento dos Dados

O dataset bruto (`bi.csv`), contendo 77 registros, foi submetido a um processo extensivo de limpeza para garantir a qualidade da análise. As etapas incluíram:

* **Tratamento de Valores Ausentes:** Os 2 valores nulos na coluna `Python` foram preenchidos utilizando a média da coluna (imputação).
* **Padronização de Dados Categóricos:** Colunas como `gender`, `prevEducation`, `country` e `residence` foram padronizadas para corrigir inconsistências, erros de digitação e variações de formato.
* **Remoção de Colunas Irrelevantes:** As colunas de identificação (`fNAME`, `lNAME`) foram removidas.
* **Análise de Outliers:** Uma análise com boxplots identificou outliers que, por serem considerados valores plausíveis no contexto, foram mantidos.

## 3. Análise Exploratória de Dados (EDA)

Com os dados limpos, foram geradas visualizações para extrair insights e entender as relações entre as variáveis.

### Perfil dos Alunos
O histograma de idades revelou que a maioria dos participantes do programa está concentrada na faixa dos 20 aos 40 anos.

<img width="622" height="403" alt="image" src="https://github.com/user-attachments/assets/f3d8ac0c-100e-4cb1-8e12-8ac009ae59f2" />

### Relação entre Esforço e Resultado
A análise da relação entre horas de estudo e a nota em Python mostrou uma **forte correlação positiva**, indicando que o esforço do aluno é um fator determinante para o sucesso.

<img width="624" height="402" alt="image" src="https://github.com/user-attachments/assets/8ce8d0df-1cd4-484e-aa8d-d7dab83f64e4" />

## 4. Modelagem Preditiva

Para avaliar o poder preditivo das características dos alunos, foram construídos e comparados dois modelos de Machine Learning para prever a nota final em `Python`.

1.  **Preparação:** As features de texto foram convertidas em formato numérico via One-Hot Encoding. Os dados foram divididos em 80% para treino e 20% para teste.
2.  **Modelos:** Foram treinados um modelo de **Regressão Linear** (como baseline) e um modelo de **Random Forest Regressor**.

## 5. Resultados e Conclusão

A performance dos modelos foi comparada utilizando o Coeficiente de Determinação (R²):

* **Regressão Linear (R²):** 0.67 (67%)
* **Random Forest (R²):** 0.49 (49%)

O modelo de Regressão Linear apresentou um desempenho superior neste cenário. Para entender os drivers de performance, foi realizada uma análise de importância de features com o modelo Random Forest.

### Análise de Importância de Features
A análise revelou que `studyHOURS` (Horas de Estudo) é, de longe, o fator mais preditivo para a nota final.

<img width="741" height="519" alt="image" src="https://github.com/user-attachments/assets/d0a26705-455f-411a-99ee-799e5eaa1b2a" />

**Recomendação Estratégica para a "Walsoft":** A análise quantitativa confirma que o engajamento do aluno (`studyHOURS`) é o principal driver de sucesso, superando fatores demográficos e de educação prévia. Recomenda-se que a instituição invista em mecanismos para incentivar e monitorar as horas de estudo, pois este é o fator mais correlacionado ao desempenho.

## 6. Ferramentas Utilizadas
* **Linguagem:** Python
* **Bibliotecas:** Pandas, Numpy, Seaborn, Matplotlib, Scikit-learn
* **Ambiente:** Jupyter Notebook
