# IT Support Dashboard

**Dashboard de suporte de TI com dataset CSV fictício, dicionário de dados e guia de KPIs/Power BI.**

---

## 📋 Visão Geral / Overview

Repositório contendo um dataset CSV fictício e limpo de chamados de suporte de TI, juntamente com um dicionário de dados, guia de Power BI/Power Query, KPIs exemplificadas e medidas DAX.

Repository containing a clean, fictional CSV dataset of IT support tickets, along with a data dictionary, Power BI/Power Query guide, example KPIs, and DAX measures.

---

## ⚠️ Aviso / Disclaimer

> **Projeto Pessoal / Laboratório / Personal Project / Laboratory Project**
>
> Este projeto é destinado apenas para fins educacionais e de laboratório. O arquivo PBIX deve ser montado no Power BI Desktop — não pode ser criado diretamente no navegador. Os dados são fictícios.
>
> This project is for educational and laboratory purposes only. The PBIX file must be built in Power BI Desktop — it cannot be created directly in the browser. The data is fictional.

---

## 📁 Estrutura do Projeto / Project Structure

```
it-support-dashboard/
├── README.md
├── data/
│   ├── tickets.csv            # Dataset fictício de chamados
│   └── tickets_dictionary.md  # Dicionário de dados
├── guide/
│   ├── power_bi_guide.md      # Guia de criação no Power BI
│   ├── power_query_steps.md   # Passos no Power Query
│   └── kpi_list.md            # Lista de KPIs recomendados
└── dax/
    └── example_measures.md    # Medidas DAX exemplificadas
```

---

## 🚀 Como Usar / How to Use

1. Abra o Power BI Desktop
2. Importe o arquivo `data/tickets.csv`
3. Siga o guia em `guide/power_bi_guide.md`
4. Configure os KPIs conforme `guide/kpi_list.md`
5. Implemente as medidas DAX de `dax/example_measures.md`

---

## 📊 Dicionário de Dados / Data Dictionary

| Coluna | Tipo | Descrição |
|--------|------|-----------|
| ticket_id | Integer | ID único do chamado |
| titulo | Text | Título do chamado |
| solicitante | Text | Nome do solicitante |
| setor | Text | Setor/Departamento |
| categoria | Text | Categoria do chamado |
| prioridade | Text | Prioridade (Baixa/Média/Alta/Crítica) |
| status | Text | Status (Aberto/Em Andamento/Resolvido/Fechado) |
| data_abertura | Date | Data de abertura |
| data_resolucao | Date | Data de resolução |
| tempo_resolucao_horas | Integer | Tempo de resolução em horas |
| satisfacao | Integer | Nota de satisfação (1-5) |

Veja `data/tickets_dictionary.md` para detalhes completos.

---

## 📈 KPIs Recomendados / Recommended KPIs

- **MTTR** (Mean Time To Resolution): Tempo médio de resolução
- **Volume de Chamados**: Total de chamados por período
- **SLA de Primeira Resposta**: % de chamados respondidos dentro do SLA
- **Taxa de Resolução no 1º Contato**: % resolvidos na primeira interação
- **Satisfação do Cliente**: Média das notas de satisfação
- **Chamados por Categoria**: Distribuição por tipo
- **Chamados por Setor**: Distribuição por departamento

---

## 🧮 Medidas DAX Exemplificadas / Example DAX Measures

```dax
-- Tempo Médio de Resolução
MTTR = AVERAGE(tickets[tempo_resolucao_horas])

-- Chamados por Mês
Total Chamados = COUNTROWS(tickets)

-- Chamados Abertos
Chamados Abertos = CALCULATE(
    COUNTROWS(tickets),
    tickets[status] = "Aberto"
)

-- Satisfação Média
Satisfacao Media = AVERAGE(tickets[satisfacao])

-- Taxa de Resolução (resolvidos/total)
Taxa de Resolucao = DIVIDE(
    CALCULATE(COUNTROWS(tickets), tickets[status] = "Resolvido"),
    COUNTROWS(tickets),
    0
)
```

Veja `dax/example_measures.md` para mais exemplos.

---

## 📝 Guia Power BI / Power BI Guide

Consulte `guide/power_bi_guide.md` e `guide/power_query_steps.md` para instruções detalhadas.

### Passos Resumidos / Summary Steps

1. **Importar Dados**: Power BI Desktop → "Get Data" → CSV
2. **Power Query**: Limpar e transformar dados
3. **Modelagem**: Criar relações se necessário
4. **Visualizações**: Criar gráficos, tabelas, KPIs
5. **Medidas DAX**: Implementar medidas calculadas
6. **Dashboard**: Montar layout final

---

## 🚫 Limitações / Limitations

- Dados são 100% fictícios — gerados para fins educacionais
- PBIX não incluído — deve ser construído no Power BI Desktop
- Sem autenticação ou acesso a dados reais
- Não testado com conjuntos de dados reais de produção
- Uso apenas laboratorial/educacional

---

## 📝 Licença / License

Projeto pessoal / laboratório. Uso educacional.
