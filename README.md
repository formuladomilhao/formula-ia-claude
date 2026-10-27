# Fórmula IA para Claude

Converse com a sua operação na Fórmula IA, a plataforma que reúne CRM, atendimento omnichannel, automações e inteligência artificial. Com o plugin, o Claude consulta os funis, as oportunidades, os contatos, os atendimentos, os canais, os indicadores, a agenda e as tarefas da sua empresa, e segue o jeito certo de usar cada informação.

Funciona no claude.ai, no Claude Desktop, no Cowork e no Claude Code.

## O que vem no plugin

- **Conector Fórmula IA**: o servidor MCP oficial em `https://mcp.formulaia.ai/crm`.
- **Skills**:
  - `diagnostico-da-conta`: raio-x de canais, filas, usuários, etiquetas, funis, lembretes e campanhas.
  - `funil-de-vendas`: funis, etapas e oportunidades; move uma oportunidade só com a sua confirmação.
  - `atendimentos`: fila de atendimentos, resumo da conversa e rascunho de resposta; envia só com a sua confirmação.
  - `indicadores-de-atendimento`: relatório por período, sem números estimados.
  - `rotina-do-dia`: compromissos, tarefas e atendimentos aguardando; agenda só com a sua confirmação.

## Antes de começar

- Uma empresa ativa na Fórmula IA.
- Para conectar: o e-mail e a senha de um **administrador** da empresa, ou a URL base e o token de uma API criada no menu **API → Nova API** do CRM.

## Instalar

- **claude.ai, Desktop e Cowork**: o plugin ainda não está no diretório do Claude. Até lá, compacte o conteúdo deste repositório num ZIP, com a pasta `.claude-plugin` na raiz, e envie em **Customize → Plugins → Upload plugin**.
- **Claude Code**:

```
/plugin marketplace add formuladomilhao/formula-ia-claude
/plugin install formula-ia@formula-ia
```

## Como conectar

1. Instale o plugin e abra a aba **Connectors** dele (no Claude Code, rode `/mcp`).
2. Conecte o **Fórmula IA**. Abre a tela de login da Fórmula IA em `mcp.formulaia.ai`.
3. Escolha **Entrar com a conta do CRM** (e-mail e senha de administrador) ou **Já tenho a URL base e o token**.
4. Pronto. Peça, por exemplo: "Faça um diagnóstico da minha conta", "Quais são meus funis e etapas?" ou "O que tenho para hoje?".

Cada login dá acesso apenas ao CRM da empresa que entrou. Para desconectar, remova o conector no Claude. A equipe da Fórmula IA também pode encerrar a conexão da empresa a pedido.

## Consultas e ações

As consultas são marcadas como somente leitura e rodam sem pedir confirmação. Ações como responder um cliente, mover uma oportunidade ou criar um compromisso só aparecem quando estão habilitadas no servidor da Fórmula IA, e o Claude pede confirmação antes de cada uma. Mensagens enviadas chegam aos seus clientes de verdade.

## Dados

- O plugin não guarda dados no seu computador nem chama outros serviços. Todas as chamadas vão para o servidor da Fórmula IA em `mcp.formulaia.ai`, que consulta a API da sua conta na plataforma Fórmula IA.
- As respostas trazem para a conversa dados do seu CRM: nomes, telefones, e-mails e campos de contatos, mensagens e notas de atendimentos, usuários da equipe, oportunidades, agenda e indicadores.
- No primeiro login com e-mail e senha, o servidor cria na sua empresa uma API chamada "MCP Fórmula IA" (ou reaproveita a que já existe) e guarda o token dela cifrado. A senha do administrador só confere o login e não é guardada.
- [Política de privacidade](https://formulaia.ai/privacidade/) e [Termos de serviço e uso](https://formulaia.ai/termos/) da Fórmula IA.

## Suporte

Abra uma issue neste repositório. As issues são públicas: não coloque nelas senhas, tokens, telefones nem dados de clientes.

## Licença

MIT. Veja [LICENSE](LICENSE).
