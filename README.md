# Workshop de IA — Alphametrics

> Como aplicar IA na sua empresa na prática — do stack zerado ao primeiro projeto rodando.

## Se você chegou aqui

Você provavelmente está (ou vai estar) na imersão de empresários do coach Sérgio Noronha (Febracis), num workshop apresentado pela [Alphametrics](https://alphametrics.com.br) sobre **como aplicar IA na sua empresa na prática**.

Este repositório é o **roteiro passo a passo** desse workshop. É hands-on: no fim, você vai enviar uma mensagem no WhatsApp usando um agente de IA que **você mesmo montou**.

## Pra quem é este material

Empresários **sem background técnico**. Assume que você:

- Nunca abriu um terminal
- Nunca usou npm, git, ssh ou nenhuma dessas siglas
- Não tem conta em nenhum serviço técnico (Contabo, Cloudflare, Anthropic, GitHub, etc)
- Vai criar **absolutamente tudo do zero**, ao vivo, junto com os outros

## O que você vai ter no fim

1. **VS Code** — editor de código
2. **Node.js** — rodador do Claude Code
3. **Git** — versionamento
4. **Claude Code** — seu novo assistente
5. **VPS Contabo** — servidor próprio na nuvem (~R$50/mês)
6. **Domínio próprio** — endereço do seu servidor (~R$40/ano)
7. **Cloudflare** — DNS configurado
8. **MCP da VPS** — Claude Code controlando sua VPS diretamente
9. **Evolution API** — motor de WhatsApp na sua VPS
10. **WhatsApp conectado** e mensagem enviada via IA — **momento eureka**

## Como usar este repositório

1. Siga os arquivos em [`passos/`](./passos) na ordem numérica.
2. Os passos **1 a 5** você lê e faz sozinho (com o Atilio ajudando na sala).
3. A partir do passo **6**, você roda `claude` no diretório deste repositório e o **Claude Code assume a condução** — ele lê automaticamente o arquivo [`CLAUDE.md`](./CLAUDE.md) e passa a te guiar comando por comando.

## O insíght que faz tudo funcionar

**Você não precisa saber. Você só precisa perguntar.**

Se travar em qualquer momento, cole o erro no Claude Code e pergunte o que fazer. É assim que times inteiros de empresas não-técnicas viraram produtivos com IA em poucas semanas.

## Estrutura

```
workshop-ia/
├── README.md            ← você está aqui
├── CLAUDE.md            ← instruções que o Claude Code lê automaticamente
├── passos/              ← roteiro numerado, siga na ordem
├── troubleshooting/     ← quando algo dá errado
└── configs/             ← templates de configuração prontos
```

---

[Alphametrics](https://alphametrics.com.br) · IA aplicada ao seu negócio
