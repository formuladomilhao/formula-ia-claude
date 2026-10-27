---
name: rotina-do-dia
description: Monta a rotina do dia ou da semana na Fórmula IA — compromissos, tarefas e atendimentos aguardando — e agenda novos itens com confirmação. Use quando o usuário perguntar o que tem para hoje, pedir a agenda, as tarefas, um resumo do dia ou quiser marcar um compromisso ou criar uma tarefa.
---

# Rotina do dia

## Consultar

1. Chame `listar_agenda_e_tarefas` com `tipo` `ambos`, `pagina` 1 e `limite` 100.
2. Filtre pelo dia pedido (hoje, no fuso de São Paulo, se nada for dito) usando as datas que vieram em cada item.
3. Separe em **Compromissos** (com horário) e **Tarefas** (com prazo). Mantenha as datas e os status como retornados.
4. Se vierem 100 itens, avise que pode haver mais e ofereça a página seguinte.
5. Para completar o dia, chame `listar_tickets` com `status` `pending` e mostre quantos atendimentos estão aguardando.

## Agendar

Só quando o usuário pedir, e só se a ferramenta `agendar` estiver disponível (as ações podem estar desligadas no servidor):

1. Para um compromisso com cliente, confirme título, data, hora de início e fim e o contato. Um compromisso dispara os lembretes automáticos configurados na conta; diga isso.
2. Para uma tarefa da equipe, confirme título e prazo.
3. Mostre o resumo e chame `agendar` depois do "sim".
