# Passo 03 — Instalar MCP da VPS

> Conduzido pelo Claude.

## Objetivo

Instalar o MCP (Model Context Protocol) da VPS no seu Claude. A partir daqui, o Claude opera sua VPS diretamente — sem voce ter que ficar copiando comandos.

## O que voce precisa em maos

- **IP da VPS** (do email da Contabo)
- **Senha root** (a que voce definiu)

## Passo a passo

O Claude vai fazer isto pra voce. Ele vai:

1. Perguntar seu IP e senha da VPS
2. Configurar um MCP chamado `vps-workshop` que aponta pra sua VPS
3. Testar a conexao
4. Confirmar que o Claude consegue rodar comandos no servidor

### Se algo der errado

**Erro de conexao SSH:** verifica se o IP esta correto (nao confunde com IPs de outros servidores). Verifica se a senha nao tem espacos no comeco/fim.

**"Timeout":** a VPS ainda pode estar ativando. Aguarda 5 minutos e tenta de novo.

**Nao sei resolver:** cola o erro no Claude e ele vai tentar diagnosticar. Se travar, chama o Atilio na sala.

## Como saber que funcionou

O Claude vai rodar um comando de teste (`hostname` ou `whoami`) na sua VPS e mostrar o resultado. Se aparecer o nome do seu servidor Contabo, funcionou.
