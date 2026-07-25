# Passo 04 — Instalar Evolution API na VPS

> Conduzido pelo Claude — ele instala tudo pra voce usando o MCP da VPS.

## O que eh Evolution API

Projeto open source que permite enviar/receber mensagens de WhatsApp de forma programatica. E o **motor** que vai ligar seu Claude ao seu WhatsApp.

Zero custo de licenca — codigo publico mantido por comunidade.

## O que o Claude vai fazer

1. Conectar na sua VPS via o MCP configurado no passo anterior
2. Instalar Docker (se ainda nao tiver)
3. Baixar imagem oficial do Evolution API
4. Configurar variaveis de ambiente (API key, porta, etc)
5. Subir o servico Evolution
6. Testar se a API responde

## Tempo estimado

~5-10 minutos, dependendo da velocidade da VPS.

## Voce so precisa

- Confirmar quando o Claude perguntar ("posso rodar tal comando?")
- Se o Claude gerar uma chave API (long random string) — **anota**. Voce vai usar no proximo passo.

## Como saber que funcionou

O Claude vai abrir a URL do painel Evolution (algo tipo `http://SEU_IP:8080/manager`) e voce vai ver a tela do gerenciador.
