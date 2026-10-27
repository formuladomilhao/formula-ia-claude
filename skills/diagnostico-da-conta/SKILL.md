---
name: diagnostico-da-conta
description: Faz um raio-x da conta Fórmula IA conectada — canais e se estão conectados, filas, usuários, etiquetas, funis com etapas, lembretes e campanhas. Use quando o usuário pedir diagnóstico, visão geral ou auditoria da conta, perguntar "como está minha conta" ou antes de configurar funis e réguas.
---

# Diagnóstico da conta

1. Chame `diagnosticar_conta` do conector Fórmula IA, sem argumentos. A conta é a que o usuário conectou no login; não há parâmetro de conta. A resposta vem em resumo (ids, nomes e status); só passe `detalhe: "completo"` se o usuário pedir um campo que o resumo não traz.
2. Monte a resposta nesta ordem:
   - **Resumo**: uma linha com as contagens que vieram no retorno (canais, filas, usuários, etiquetas, funis, campanhas).
   - **Canais**: nome e estado de cada um, exatamente como retornado. Destaque os que não estão conectados.
   - **Funis**: cada funil com as etapas na ordem.
   - **Equipe e organização**: filas, quantidade de usuários e etiquetas principais.
   - **Pontos de atenção**: só fatos do retorno, como canal desconectado, funil sem etapas ou nenhum lembrete de agendamento.
3. Uma seção que voltou como `{ "erro": ... }` não está vazia: diga que não foi possível ler aquela parte e mostre a mensagem. Nunca a apresente como zero.
4. Liste nomes e e-mails de usuários só se o usuário pedir.
5. Não proponha nem faça alterações. Se o usuário quiser configurar a conta, descreva o plano (funil, etapas, etiquetas, réguas) e espere a aprovação antes de qualquer ferramenta de escrita.

Não cole o JSON bruto na resposta.
