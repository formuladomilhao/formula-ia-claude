---
name: atendimentos
description: Acompanha atendimentos (tickets) e conversas da Fórmula IA — lista por status, resume a conversa, sugere a resposta e, só com confirmação, responde ao cliente. Use quando o usuário falar de atendimentos, tickets, clientes esperando, fila, conversa com um cliente ou pedir para responder alguém.
---

# Atendimentos

## Ver e resumir

1. Para a fila, chame `listar_tickets` com `status` `open` (em atendimento), `pending` (aguardando) ou `closed`. Para um cliente, use `buscar_contatos` e depois `ver_ticket` com `numero`.
2. Para entender um caso, chame `ver_ticket` com `ticket_id` e `ler_conversa` com o mesmo `ticket_id` (traz mensagens e notas internas; use `busca` para achar um assunto).
   As listas vêm em resumo: o cliente, o atendente e a fila aparecem só com id e nome. Para os dados completos de um cliente, use `ver_contato`; para tudo de uma lista, passe `detalhe: "completo"`.
3. Resuma em até cinco linhas: quem é o cliente, o que pediu, o que já foi feito e o próximo passo.
4. Se o cliente parece sem resposta, chame `status_canais` para conferir se o canal do atendimento está conectado.

## Responder

As ferramentas de envio podem estar desligadas no servidor. Se não estiverem disponíveis, entregue só o rascunho.

1. Escreva o rascunho da resposta e mostre ao usuário junto com o destino (atendimento e nome do cliente).
2. Envie **somente** depois de uma confirmação explícita para aquele texto e aquele destino. Uma confirmação vale para um envio.
3. Com atendimento aberto, use `responder_ticket` (`ticket_id`, `texto`). Use `enviar_mensagem` só para quem não tem atendimento e com um número que o usuário confirmou.
4. Fora da janela de 24 horas da API oficial do WhatsApp, a mensagem livre não sai: use `enviar_template_waba` com um modelo aprovado.
5. Para registrar algo só para a equipe, use `nota_interna`, que o cliente não vê.
6. Nunca envie para números que o usuário não indicou nem dispare mensagens em lote a partir desta skill.
