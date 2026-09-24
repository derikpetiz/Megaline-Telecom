# 📞 Megaline Telecom: Análise Estatística de Planos Pré-Pagos

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-1.5+-150458.svg)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12+-3776AB.svg)
![SciPy](https://img.shields.io/badge/SciPy-1.10+-8CAAE6.svg)

## 📌 Visão Geral do Projeto

Este projeto realiza uma Análise Exploratória de Dados (EDA) e Teste de Hipóteses Estatísticas para a **Megaline**, uma empresa de telecomunicações que oferece dois planos pré-pagos: **Surf** e **Ultimate**.

O objetivo principal é analisar o comportamento de consumo de uma amostra de 500 clientes para determinar qual dos planos gera maior receita. Esta informação serve de subsidio para o departamento comercial otimizar a alocação do orçamento de publicidade.

---

## 📊 Regras de Negócio e Termos dos Planos

| Métrica / Tarifa | Plano Surf | Plano Ultimate |
| :--- | :--- | :--- |
| **Mensalidade Base** | **$20** | **$70** |
| **Pacote Mensal Incluído** | 500 minutos <br> 50 SMS <br> 15 GB | 3.000 minutos <br> 1.000 SMS <br> 30 GB |
| **Minuto Excedente** | $0,03 / min | $0,01 / min |
| **SMS Excedente** | $0,03 / mensagem | $0,01 / mensagem |
| **GB Excedente** | $10 / GB | $7 / GB |

*Nota: As chamadas individuais são arredondadas para cima (próximo minuto). O tráfego mensal de internet é arredondado para o Gigabyte superior ao final do mês.*

---

## 🛠️ Tecnologias e Bibliotecas Utilizadas

- **Linguagem:** Python 3.8+
- **Manipulação de Dados:** `pandas`, `numpy`
- **Visualização de Dados:** `matplotlib`, `seaborn`
- **Análise Estatística:** `scipy.stats` (Teste T de Student)

---

## 🔍 Etapas e Metodologia

1. **Pré-processamento e Limpeza de Dados:**
   - Conversão de colunas de data para o tipo `datetime`.
   - Aplicação de regras de negócio: arredondamento de chamadas individuais para o minuto superior.
   - Tratamento de inconsistências e valores ausentes (ex: chamadas com duração de 0 minutos representando chamadas perdidas).
2. **Engenharia de Recursos e Agregação:**
   - Agrupamento do consumo dos usuários (chamadas, mensagens e tráfego de dados) em base mensal.
   - Conversão do volume mensal de Megabytes para Gigabytes (arredondando para cima).
   - Cálculo da receita mensal individual gerada por cada usuário, considerando limites do plano e cobranças por excesso.
3. **Análise Exploratória de Dados (EDA):**
   - Comparação das médias e distribuições de minutos falados, mensagens enviadas e GBs consumidos entre os dois planos ao longo dos meses.
   - Análise de variância e desvio padrão do comportamento dos clientes.
4. **Testes de Hipóteses Estatísticas:**
   - **Hipótese 1:** A receita média dos usuários dos planos Ultimate e Surf difere entre si.
   - **Hipótese 2:** A receita média dos usuários da região de NY-NJ difere da receita dos usuários de outras regiões.

---

## 📈 Principais Insights e Conclusões

- **Driver de Receita:** O **Plano Surf** frequentemente gera uma receita total expressiva por meio de taxas de excedente (especialmente consumo extra de dados de internet), apesar de possuir uma mensalidade base significativamente menor que o plano Ultimate.
- **Comportamento de Consumo:** Clientes de ambos os planos apresentam médias de duração de chamadas semelhantes, porém o limite de 15 GB do Plano Surf é frequentemente superado, gerando cobranças adicionais recorrentes.

---

## 🚀 Como Executar o Projeto

1. Clone o repositório:
   ```bash
   git clone [https://github.com/derikpetiz/telecom-megaline-plan-analysis.git](https://github.com/derikpetiz/telecom-megaline-plan-analysis.git)
   cd telecom-megaline-plan-analysis
