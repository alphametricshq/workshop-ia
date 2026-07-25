# Workshop de IA — Alphametrics

> Como aplicar IA na sua empresa na prática — do stack zerado ao primeiro projeto rodando.

## Se você chegou aqui

Você provavelmente está (ou vai estar) na imersão de empresários do coach Sérgio Noronha (Febracis), num workshop apresentado pela [Alphametrics](https://alphametrics.com.br) sobre **como aplicar IA na sua empresa na prática**.

Este repositório é o **roteiro passo a passo** desse workshop. É hands-on: no fim, você vai enviar uma mensagem no WhatsApp usando um agente de IA que **você mesmo montou** — e ainda vai criar um site.

## Pra quem é este material

Empresários **sem background técnico**. Assume que você:

- Nunca abriu um terminal
- Nunca usou nenhuma sigla técnica (git, ssh, API, MCP…)
- Não tem conta em nenhum serviço técnico (Contabo, Anthropic…)
- Vai criar **absolutamente tudo do zero**, ao vivo, junto com os outros

---

## Os 3 passos pra começar

### 1. Baixar o Claude Desktop

Baixe no site oficial da Anthropic — [claude.com/download](https://claude.com/download). Escolha Mac ou Windows.

### 2. Criar conta Anthropic + assinar Claude Pro

Ao abrir o Claude Desktop pela primeira vez, ele vai pedir pra você fazer login ou criar conta. Crie sua conta e assine o plano **Claude Pro** (~R$99/mês). O plano Pro dá acesso ao Claude Code, que é o que a gente vai usar.

### 3. Colar este prompt na aba **Code**

Dentro do Claude Desktop, clique na aba **Code** (no topo). Vai abrir uma tela pra conversar com o Claude Code. Cole o prompt abaixo (o texto inteiro, do começo até o fim) e aperte enter:

```
Olá! Estou no workshop de IA da Alphametrics do Sérgio Noronha.

Por favor:
1. Se o git não estiver instalado no meu computador, instale primeiro
   (pergunta antes).
2. Clona o repositório https://github.com/alphametricshq/workshop-ia.git
   dentro da minha pasta Documents.
3. Entra na pasta clonada.
4. Lê o arquivo CLAUDE.md.
5. Me guia pelo workshop passo a passo, em português, começando por
   perguntar meu sistema operacional (Windows ou Mac).
```

Depois de colar e apertar enter, **o Claude assume a condução** — ele lê automaticamente o arquivo [`CLAUDE.md`](./CLAUDE.md) e passa a te guiar comando por comando.

_(O mesmo prompt também está salvo em [prompt-inicial.txt](./prompt-inicial.txt) pra facilitar copy-paste.)_

---

## O que você vai ter no fim

1. **Git** — pra baixar este repositório no seu computador
2. **Claude Desktop + Pro** — seu novo assistente de IA, com aba **Code**
3. **VPS Contabo** — servidor próprio na nuvem (~R$50/mês)
4. **MCP da VPS** — Claude controlando sua VPS diretamente
5. **Evolution API** — motor de WhatsApp na sua VPS
6. **WhatsApp conectado** e mensagem enviada via IA — **momento eureka 1**
7. **Site publicado na Vercel** — **momento eureka 2** (se sobrar tempo)

## Custo aproximado

Cerca de **R$ 160**: VPS Contabo (~R$50/mês) + Claude Pro (~R$99/mês).

## O insíght que faz tudo funcionar

**Você não precisa saber. Você só precisa perguntar.**

Se travar em qualquer momento, cola o erro no Claude e pergunta o que fazer. É assim que times inteiros de empresas não-técnicas viraram produtivos com IA em poucas semanas.

## Depois do workshop — próximos passos

Depois do momento eureka, possíveis próximos passos:

- **Explorar a aba Cowork** do Claude Desktop — IA agindo no seu computador (Excel, sistema web da empresa)
- **Contratar domínio próprio** — URL bonita (`seunegocio.com`)
- **Cloudflare + HTTPS** — profissionalizar a stack
- **Automações de WhatsApp mais complexas** — integração com seu ERP
- **Dashboards e relatórios** — seu Claude conectado à base de dados da empresa

O Claude te guia em qualquer um. É só pedir.

## Estrutura

```
workshop-ia/
├── README.md            ← você está aqui
├── prompt-inicial.txt   ← o prompt que você cola no Claude Desktop
├── CLAUDE.md            ← instruções que o Claude lê automaticamente
├── passos/              ← roteiro numerado do workshop
├── troubleshooting/     ← quando algo dá errado
└── configs/             ← templates prontos
```

---

[Alphametrics](https://alphametrics.com.br) · IA aplicada ao seu negócio
