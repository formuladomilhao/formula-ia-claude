---
name: indicadores-de-atendimento
description: Relatório de indicadores de atendimento da Fórmula IA por período — volume por status, por canal, por fila, por atendente, tempos, motivos de encerramento, evolução e avaliações. Use quando o usuário pedir métricas, relatório, desempenho da equipe, números do mês ou comparação entre períodos.
---

# Indicadores de atendimento

1. Converta o período pedido em datas `AAAA-MM-DD`, no fuso de São Paulo. Sem período, use o mês atual até hoje e diga isso na resposta. Se o pedido for ambíguo ("semana passada" sem referência), confirme as datas.
2. Escolha as métricas de `indicadores_atendimento` que respondem à pergunta e chame uma vez para cada:
   - `status` — volume por situação
   - `canais`, `filas`, `por_atendente`, `usuarios` — distribuição
   - `tempos` — tempos de atendimento
   - `motivos` — motivos de encerramento
   - `evolucao`, `evolucao_valor`, `evolucao_canais` — série no período
   - `avaliacoes` — avaliações dos clientes. Essa métrica **não filtra por data**: traz a primeira página de avaliações; diga isso ao usuário.
3. Apresente os números exatamente como vieram, com o período no título. Use tabela quando houver mais de três linhas.
4. Não calcule receita, conversão ou causas que o retorno não traga. Uma comparação entre períodos só vale com duas consultas, uma para cada período.
5. Se uma métrica falhar, diga qual e mostre a mensagem; não monte o relatório sem ela.
