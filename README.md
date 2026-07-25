# Workshop de IA — Alphametrics

> Como aplicar IA na sua empresa na prática — do stack zerado ao primeiro projeto rodando.

## Se você chegou aqui

Você provavelmente está (ou vai estar) na imersão de empresários do coach Sérgio Noronha (Febracis), num workshop apresentado pela [Alphametrics](https://alphametrics.com.br) sobre **como aplicar IA na sua empresa na prática**.

Este repositório é o **roteiro passo a passo** desse workshop. É hands-on: no fim, você vai enviar uma mensagem no WhatsApp usando um agente de IA que **você mesmo montou**.

## Pra quem é este material

Empresários **sem background técnico**. Assume que você:

- Nunca abriu um terminal
- Nunca usou nenhuma sigla técnica (git, ssh, API, MCP…)
- Não tem conta em nenhum serviço técnico (Contabo, Anthropic, GitHub, etc)
- Vai criar **absolutamente tudo do zero**, ao vivo, junto com os outros

## O que você vai ter no fim

1. **Git** — pra baixar este repositório no seu computador
2. **Claude Desktop** (app) — seu novo assistente de IA, com aba **Code**
3. **Conta Anthropic + Claude Pro** — acesso ao Claude Code (~R$99/mês)
4. **VPS Contabo** — servidor próprio na nuvem (~R$50/mês)
5. **MCP da VPS** — Claude controlando sua VPS diretamente
6. **Evolution API** — motor de WhatsApp na sua VPS
7. **WhatsApp conectado** e mensagem enviada via IA — **momento eureka**

## Custo aproximado

Cerca de **R$ 160**: VPS Contabo (~R$50/mês) + assinatura Claude Pro (~R$99/mês).

## Como usar este repositório

1. Siga os arquivos em [`passos/`](./passos) na ordem numérica.
2. Os passos **1 a 6** você lê e faz sozinho (com o Atilio ajudando na sala).
3. A partir do passo **7**, você abre a aba **Code** no Claude Desktop, aponta pra pasta deste repositório, e o **Claude assume a condução** — ele lê automaticamente o arquivo [`CLAUDE.md`](./CLAUDE.md) e passa a te guiar passo a passo.

## O insíght que faz tudo funcionar

**Você não precisa saber. Você só precisa perguntar.**

Se travar em qualquer momento, cola o erro no Claude e pergunta o que fazer. É assim que times inteiros de empresas não-técnicas viraram produtivos com IA em poucas semanas.

## Depois do workshop — próximos passos

Quando o momento eureka rolar, você vai querer expandir. Possíveis próximos passos:

- **Explorar a aba Cowork** do Claude Desktop — IA agindo no seu computador (Excel, sistema web da empresa, planilha)
- **Contratar domínio próprio** — pra ter URL bonita (`seunegocio.com`) em vez de IP puro
- **Cloudflare + HTTPS** — profissionalizar a stack
- **Criar site na Vercel** — landing page ou site institucional do zero, tudo com Claude
- **Automações de WhatsApp mais complexas** — fluxos, integração com seu ERP
- **Dashboards e relatórios** — seu Claude conectado à sua base de dados

O Claude te guia em qualquer um desses. É só pedir.

## Estrutura

```
workshop-ia/
├── README.md            ← você está aqui
├── CLAUDE.md            ← instruções que o Claude lê automaticamente
├── passos/              ← roteiro numerado, siga na ordem
├── troubleshooting/     ← quando algo dá errado
└── configs/             ← templates de configuração prontos
```

---

[Alphametrics](https://alphametrics.com.br) · IA aplicada ao seu negócio
