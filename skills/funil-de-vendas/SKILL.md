---
name: funil-de-vendas
description: Consulta funis de vendas (pipelines), etapas e oportunidades na Fórmula IA, e move ou atualiza oportunidades com confirmação. Use quando o usuário perguntar sobre funil, pipeline, etapas, oportunidades, negócios em andamento, onde está um cliente no funil ou quiser mover uma oportunidade.
---

# Funil de vendas

## Consultar

1. Chame `ver_funil`. Sem `pipeline_id` ele traz todos os funis com as etapas em ordem. Para um funil só, passe o `pipeline_id`.
2. As oportunidades vêm em páginas de 20 (`pagina`, `limite` até 100). Diga quando a lista pode ter mais páginas e ofereça buscar a próxima; não trate a primeira página como o total.
3. Agrupe as oportunidades pela etapa informada em cada uma. Some valores só quando o retorno trouxer o campo de valor, e diga quantas oportunidades ficaram sem valor.
4. Não estime faturamento, conversão ou previsão que o retorno não traga.

## Mover ou atualizar uma oportunidade

Só quando o usuário pedir, e só se a ferramenta `salvar_oportunidade` estiver disponível (as ações podem estar desligadas no servidor):

1. Identifique a oportunidade e a etapa de destino pelos IDs que vieram de `ver_funil`.
2. Mostre o que vai mudar (oportunidade, etapa atual → nova etapa, valor ou status) e peça confirmação.
3. Depois do "sim", chame `salvar_oportunidade` com `oportunidade_id` e só os campos que mudam.
4. Confirme o resultado com o resumo que a ferramenta devolveu.
