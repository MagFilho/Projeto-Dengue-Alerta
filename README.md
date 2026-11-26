<img width="1717" height="673" alt="DengueAlerta(1)" src="https://github.com/user-attachments/assets/4d04d78f-4007-4654-a193-a00006b29d6e" />


# 📌 Dengue Alerta: Monitoramento e Correlação Bioclimática (2025)

Este repositório contém um sistema integrado de monitoramento epidemiológico que correlaciona novos casos de Dengue com fatores meteorológicos críticos (temperatura média e precipitação) para o ano de **2025**. O principal objetivo é mapear janelas climáticas favoráveis à proliferação do vetor *Aedes aegypti* utilizando dados públicos reais das agências federais do Brasil.

---

## ⚙️ Funcionalidades

* **Ingestão de Dados do Mundo Real (2025):**
  * Carregamento estruturado da base nacional de notificações de Dengue do **DATASUS** (2025), contendo mais de 1.6 milhão de registros históricos.
  * Importação e decodificação de mais de 590 estações meteorológicas automáticas do **INMET** do ano de 2025.
* **Interface de Busca Interativa no Colab:**
  * Sistema de pesquisa e filtragem de cidades via menu *Dropdown* dinâmico com autocompletação reativa baseada em `ipywidgets` para troca rápida da estação meteorológica de análise.
* **Pipeline de Engenharia de Dados (ETL):**
  * Saneamento de separadores de strings decimais brasileiros (vírgula para ponto).
  * Agrupamento e consolidação de séries temporais horárias em médias (temperatura) e somatórios (precipitação) diários.
* **Análise Estatística e Epidemiológica:**
  * Agrupamento diário para o calendário de **Semanas Epidemiológicas** (Padrão ISO).
  * Geração automatizada de matrizes de correlação de Pearson e gráficos temporais dinâmicos de eixo duplo (Casos Notificados vs. Temperatura).

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.10+
* **Interface Interativa:** `ipywidgets` / IPython Displays
* **Análise de Dados:** `pandas`, `numpy`
* **Visualização Gráfica:** `matplotlib`, `seaborn`
* **APIs Secundárias:** `openmeteo-requests` para verificação de dados históricos de referência por coordenadas geográficas.

---

## 🚀 Como Executar no GitHub / Colab

1. **Abrir o Notebook:** Importe o arquivo `.ipynb` no Google Colab ou execute-o localmente no Jupyter.
2. **Instalar Dependências:** Execute a célula inicial de instalação para garantir as dependências:
```bash
pip install pandas numpy matplotlib seaborn ipywidgets openmeteo-requests
```
3. **Selecione sua Cidade Interativamente:** Use a barra de pesquisa na seção `3.1.1` para buscar o nome da sua cidade ou região (Ex: *Mossoró - RN*, *Belo Horizonte - MG*, *Porto Alegre - RS*). Os dados climáticos da região serão instantaneamente compilados na memória.
4. **Visualize os Resultados:** Execute as células de modelagem subsequentes para plotar as curvas epidêmicas e de temperatura alinhadas pelas Semanas Epidemiológicas.
