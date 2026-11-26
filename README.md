<img width="1717" height="673" alt="DengueAlerta(1)" src="https://github.com/user-attachments/assets/4d04d78f-4007-4654-a193-a00006b29d6e" />


# 📌 Dengue Alerta: Monitoramento e Correlação Bioclimática (2025)

Este repositório contém um sistema integrado de monitoramento epidemiológico que correlaciona notificações de Dengue com fatores meteorológicos críticos (temperatura média e precipitação) para o ano de **2025**. O principal objetivo é mapear janelas climáticas favoráveis à proliferação do vetor *Aedes aegypti* utilizando dados públicos reais das agências federais do Brasil.

---

## ⚙️ Funcionalidades Implementadas

* **Ingestão de Dados Reais do DATASUS (2025):**
  * Processamento de base nacional de notificações de Dengue contendo **1.643.215 registros** de 2025.
  * Tratamento flexível de filtros estaduais via mapeamento do código de UF de 2 dígitos do IBGE.
* **Processamento de Dados Oficiais do INMET (2025):**
  * Download, descompactação e ingestão de **594 estações meteorológicas automáticas** nacionais cobrindo todo o ano de 2025.
  * Pipeline de Engenharia de Dados que unifica leituras horárias em resumos diários de temperatura média e acumulado de precipitação (chuva).
* **Interface Interativa por Cidade:**
  * Menu suspenso (*Dropdown*) dinâmico reativo alimentado por `ipywidgets` que permite filtrar e carregar instantaneamente qualquer uma das estações disponíveis na base local através de pesquisa textual amigável.
* **Análise Estatística e Epidemiológica Semanal:**
  * Agrupamento sistemático das séries diárias reais para o calendário oficial de **Semanas Epidemiológicas (ISO Week)**.
  * Matriz de correlação de Pearson entre casos e parâmetros de temperatura e precipitação.
  * Gráficos dinâmicos de eixo duplo (Y1 para evolução epidêmica semanal e Y2 para oscilações de temperatura em °C).

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.10+
* **Interface Interativa:** `ipywidgets` / IPython Displays
* **Análise de Dados:** `pandas`, `numpy`
* **Visualização Gráfica:** `matplotlib`, `seaborn`
* **API de Referência:** `openmeteo-requests` para validação meteorológica de séries históricas de referência geoespacial (2021-2023).

---

## 🚀 Como Executar no Colab

1. **Instalar Dependências:** Execute a primeira célula do notebook para instalar as bibliotecas de processamento:
   ```bash
   pip install dbfread openmeteo-requests requests-cache retry
   ```
2. **Caso haja instabilidade na fonte por onde os dados são baixados e eles não baixem automaticamente, baixe os arquivos "arboviroses_dengue_2025.csv" e "inmet_2025.zip" disponíveis neste repositório, em seguida arraste para a aba de arquivos dentro do colab    
3. **Selecionar a Estação Meteorológica:** Interaja com o menu interativo gerado por widgets para digitar e escolher sua cidade (Ex: *Mossoró - RN*, *Belo Horizonte - MG*, *Porto Alegre - RS*).
4. **Executar as Células Subsequentes:** O código irá filtrar as notificações do DATASUS para o estado correspondente da estação escolhida e plotar as matrizes de correlação de Pearson e os gráficos de monitoramento temporal.
