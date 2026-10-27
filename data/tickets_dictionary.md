# Dicionário de Dados — Tickets de Suporte

## Visão Geral

Este documento descreve a estrutura e o significado de cada coluna no arquivo `tickets.csv`, que contém dados fictícios de chamados de suporte de TI para fins educacionais.

## Estrutura

| Coluna | Tipo | Descrição | Exemplo |
|--------|------|-----------|---------|
| `ticket_id` | Integer | ID numérico único do chamado | `1001` |
| `titulo` | Text | Título curto do chamado | `"Impressora não imprime"` |
| `solicitante` | Text | Nome do funcionário que abriu o chamado | `"João Silva"` |
| `setor` | Text | Departamento/área do solicitante | `"TI"`, `"RH"`, `"Financeiro"`, `"Vendas"`, `"Administrativo"`, `"Marketing"`, `"Infraestrutura"` |
| `categoria` | Text | Categoria técnica do problema | `"Hardware"`, `"Software"`, `"Rede"`, `"Segurança"`, `"Infraestrutura"`, `"Desempenho"` |
| `prioridade` | Text | Nível de prioridade do chamado | `"Baixa"`, `"Média"`, `"Alta"`, `"Crítica"` |
| `status` | Text | Status atual do chamado | `"Aberto"`, `"Em Andamento"`, `"Resolvido"`, `"Fechado"` |
| `data_abertura` | Date | Data em que o chamado foi aberto (YYYY-MM-DD) | `"2024-01-05"` |
| `data_resolucao` | Date | Data em que o chamado foi resolvido (YYYY-MM-DD). Pode estar vazio se o chamado ainda não foi resolvido. | `"2024-01-05"` ou `""` |
| `tempo_resolucao_horas` | Integer | Tempo de resolução em horas. `0` se ainda não resolvido. | `2` ou `0` |
| `satisfacao` | Integer | Nota de satisfação do solicitante (1-5). `0` se ainda não avaliado. | `4` ou `0` |

## Notas

- Os dados são **100% fictícios** — gerados para fins educacionais e de demonstração.
- `satisfacao` pode ser `0` se o chamado ainda não foi avaliado ou não foi resolvido.
- `tempo_resolucao_horas` é `0` para chamados abertos ou em andamento.
- `data_resolucao` está vazio para chamados não resolvidos.
- Setores incluem: TI, RH, Financeiro, Vendas, Administrativo, Marketing, Infraestrutura.
- Categorias incluem: Hardware, Software, Rede, Segurança, Infraestrutura, Desempenho.

## Uso no Power BI

Este arquivo pode ser importado diretamente no Power BI Desktop para criação de dashboards e relatórios.

Para mais detalhes, consulte `guide/power_bi_guide.md`.
