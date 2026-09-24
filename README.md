# 📞 Megaline Telecom: Análise Estatística de Planos Pré-Pagos e Receita

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-1.5+-150458.svg)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12+-3776AB.svg)
![SciPy](https://img.shields.io/badge/SciPy-1.10+-8CAAE6.svg)

## 📌 Visão Geral e Contexto do Negócio

A **Megaline** é uma operadora de telefonia móvel que oferece dois planos pré-pagos aos seus clientes: **Surf** e **Ultimate**. O departamento comercial precisa entender qual dos planos gera mais receita para otimizar o investimento e o direcionamento das campanhas publicitárias.

Este projeto analisa o comportamento de consumo de uma amostra representativa de **500 usuários**, avaliando volume de chamadas, mensagens enviadas, tráfego de dados e o faturamento total gerado por cliente ao longo do ano.

---

## ❓ Hipóteses Formuladas

1. **Hipótese de Consumo de Dados:** Usuários do plano *Surf* ultrapassam o limite de franquia de dados (15 GB) com maior frequência que os usuários do plano *Ultimate* (30 GB), gerando receita significativa por cobrança excedente.
2. **Hipótese Estatística 1 (H0/H1):** 
   - **H0:** A receita média gerada pelos usuários dos planos *Surf* e *Ultimate* é igual.
   - **H1:** A receita média gerada pelos usuários dos planos *Surf* e *Ultimate* difere significativamente.
3. **Hipótese Estatística 2 (H0/H1):**
   - **H0:** A receita média dos usuários da região de *NY-NJ* é igual à receita dos usuários de outras regiões.
   - **H1:** A receita média dos usuários da região de *NY-NJ* difere da receita das demais regiões.

---

## 📊 Regras de Negócio e Termos dos Planos

| Métrica / Tarifa | Plano Surf | Plano Ultimate |
| :--- | :--- | :--- |
| **Mensalidade Base** | **$20** | **$70** |
| **Pacote Incluído** | 500 min \| 50 SMS \| 15 GB | 3.000 min \| 1.000 SMS \| 30 GB |
| **Minuto Excedente** | $0,03 / min | $0,01 / min |
| **SMS Excedente** | $0,03 / mensagem | $0,01 / mensagem |
| **GB Excedente** | $10 / GB | $7 / GB |

---

## 📈 Análise Visual e Gráficos do Projeto

### 1. Comparativo de Receita Média Mensal por Plano
![Receita Média Mensal](assets/receita_media_mensal.png)
*Figura 1: Faturamento médio mensal comparando os planos Surf e Ultimate ao longo dos doze meses.*

---

### 2. Distribuição do Consumo Mensal de Internet (GB)
![Consumo de Internet](assets/consumo_internet_gb.png)
*Figura 2: Distribuição de uso de dados em GB destacando o limite da franquia do plano Surf (15 GB) e a zona de cobrança adicional.*

---

### 3. Metodologia do Teste de Hipóteses Estatísticas
![Metodologia do Teste](assets/metodologia_testes.png)
*Figura 3: Fluxo metodológico utilizado no Teste T de Student para validação das hipóteses estatísticas.*

---

## 💡 Insights Obtidos e Conclusões

- 🟢 **O Plano Surf é a principal fonte de receita extra:** Mais de 40% dos usuários do plano Surf excedem a franquia de dados mensalmente. O custo por GB excedente ($10/GB) eleva a conta média desse plano para valores próximos ou superiores aos do plano Ultimate em diversos meses.
- 🟡 **O Volume de Chamadas e SMS não impacta substancialmente a receita:** A maioria dos usuários de ambos os planos não atinge o limite de minutos ou SMS. O tráfego de internet é o fator determinante no faturamento extra.
- 🔴 **Diferença de Receita Significativa (Teste T):** O teste t de Student rejeitou a hipótese nula com um *p-value* extremamente baixo ($p < 0.05$), confirmando estatisticamente que os planos *Surf* e *Ultimate* possuem médias de faturamento mensal diferentes.
- ⚪ **Receita Regional (NY-NJ vs. Outras Regiões):** Não foi encontrada diferença estatisticamente significativa entre a receita gerada na área metropolitana de *New York-New Jersey* e as demais cidades da amostra.

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem:** Python 3.8+
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`

---

## 🚀 Como Executar o Projeto

```bash
# 1. Clonar o repositório
git clone [https://github.com/derikpetiz/telecom-megaline-plan-analysis.git](https://github.com/derikpetiz/telecom-megaline-plan-analysis.git)
cd telecom-megaline-plan-analysis

# 2. Instalar dependências
pip install -r requirements.txt

# 3. Executar o script principal
python main.py
