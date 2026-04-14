# mvp-puc-analise-dados
Repositório para documentação do MVP produzido na Sprint de Análise de Dados e Boas Práticas, parte da pós graduação em Ciência de Dados e Analytics da PUC-RJ.

# 🚗 Previsão de Preços de Veículos Usados (Análise & Pré-processamento)

Este repositório contém o projeto de **Análise Exploratória (EDA) e Pré-processamento de Dados** focado no mercado de carros usados dos EUA (dados de 2023). O objetivo principal é transformar dados brutos de *web scraping* em um conjunto de dados estruturado e validado para modelos de regressão, auxiliando vendedores na escolha assertiva de preços.

---

## 📌 Principais Funcionalidades & Insights
- 🧹 **Limpeza e Normalização de Tipos**: Conversão de variáveis críticas (price e milage) de texto para formato numérico, removendo caracteres especiais e símbolos de moeda via RegEx.
- 🛠️ **Tratamento de Dados Ausentes**: Imputação estratégica baseada em lógica de negócio, como a identificação de veículos elétricos e a binarização da variável accident.
- ⚙️ **Feature Engineering**: Extração técnica de dados de motores (HP, Cilindrada, Turbo) e criação de agrupamentos semânticos (Brand Tiers e Model Personas).
- 📊 **Análise de Outliers Segmentada**: Implementação de técnica de IQR por nicho de mercado, preservando veículos de luxo e performance enquanto remove ruídos estatísticos.
- 🧪 **Validação de Hipóteses**: Estudo estatístico sobre a depreciação por idade, impacto da quilometragem e registro de sinistros, além da evolução da transmissão automática no mercado.

---

## 🛠 Tecnologias Utilizadas
- **Linguagem**: Python 3.x
- **Bibliotecas principais**: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, SciPy.
- **Ambiente**: Google Colab.

---

## 📂 Estrutura do Projeto

* 📄 **used_cars.csv**: Dataset original (espelhado do Kaggle/Cars.com).
* 📄 **Sprint2_MVP_Analise_de_Dados.ipynb**: Notebook principal com todo o pipeline de análise.
* 📄 **README.md**: Documentação do projeto.

---

## 🚀 Guia de Dataframes Gerados
Durante a execução, o projeto gera marcos evolutivos dos dados:
1. **df_cars**: Base processada com novas variáveis estruturadas.
2. **df_cars_clean**: Base higienizada (sem outliers) para análise estatística.
3. **df_cars_final**: Base pronta para ML (com Encoding e Normalização).
4. **df_top_segmentos**: Recorte dos 5 maiores segmentos para validação de hipóteses.

---

## 🔧 Como Executar
1. **Clonar o Repositório**:
   git clone https://github.com/izabelaandrade-pos/mvp-puc-analise-dados.git
   
2. **Execução**: 

* Google Colab: Importe o arquivo .ipynb diretamente para o Colab. O ambiente já conta com todas as bibliotecas necessárias pré-instaladas.

* Ambiente Local: Caso utilize Jupyter Notebook ou VS Code, certifique-se de ter instalado: pandas, numpy, seaborn, scikit-learn e scipy.

---

## 📝 Nota Técnica: Pipeline de Modelagem
Para garantir a **integridade preditiva** e evitar o **Data Leakage** (vazamento de dados) em etapas de treinamento, recomenda-se que a divisão entre treino e teste (Split) seja realizada **antes** das seguintes operações:
- Imputação de valores ausentes por mediana.
- Tratamento de outliers.
- Aplicação de Dummy Encoding.
- Normalização de variáveis.

Isso garante que os parâmetros estatísticos (como limites de IQR e escalas de normalização) sejam aprendidos exclusivamente no conjunto de treino.

---

## 📜 Licença
Este projeto utiliza dados sob a licença **Attribution 4.0 International (CC BY 4.0)**.
