# Passo 04 — Instalar Evolution API na VPS

> Conduzido pelo Claude — ele faz tudo via terminal integrado, usando o MCP da VPS que você instalou no passo anterior.

## O que é Evolution API

**Projeto open source** que conecta seu WhatsApp a qualquer sistema via API HTTP. Zero custo de licença. Mantido pela comunidade evolution-foundation.

- **Repositório oficial:** https://github.com/evolution-foundation/evolution-api
- **Documentação:** https://doc.evolution-api.com
- **Versão que vamos usar:** v2 (a mais atual)

É o **motor** que vai permitir você/seu Claude enviar mensagens pelo seu número de WhatsApp programaticamente. A instalação é via Docker (containers isolados) na sua VPS.

---

## O que o Claude vai fazer (você só confirma)

1. **Conectar na VPS** via MCP (já configurado no passo 03)
2. **Instalar Docker** (se não tiver)
3. **Baixar arquivo `docker-compose.yaml`** oficial do Evolution API
4. **Criar arquivo `.env`** com as credenciais que você vai usar
5. **Subir os containers** (`docker compose up -d`)
6. **Aguardar Evolution ficar online**
7. **Verificar que o Manager UI abre** em `http://SEU_IP:3000`

## Detalhes técnicos (pra o Claude entender)

O stack que vamos subir tem 3 serviços:

- **evolution-api** (porta 8080) — a API que faz o trabalho
- **evolution-manager** (porta 3000) — painel visual pra criar instances, ver QR code, monitorar
- **postgres + redis** (portas internas) — armazenamento de sessões e cache

Template de `docker-compose.yaml` pronto: [`configs/docker-compose-evolution.yaml`](../configs/docker-compose-evolution.yaml).

Template de `.env` pronto: [`configs/evolution.env`](../configs/evolution.env). O Claude vai gerar uma API key aleatória pra você (32 caracteres) — **anota essa chave**, você vai usar depois.

## Comandos que o Claude vai rodar na VPS

```bash
# 1. Verificar/instalar Docker
curl -fsSL https://get.docker.com | sh
systemctl enable --now docker

# 2. Criar diretorio
mkdir -p /opt/evolution && cd /opt/evolution

# 3. Baixar docker-compose e .env (do template do repo do workshop)
# (o Claude vai criar esses arquivos diretamente com os valores certos)

# 4. Subir os containers
docker compose up -d

# 5. Aguardar 30 segundos e verificar
docker compose ps
curl http://localhost:8080
```

## Como saber que funcionou

O Claude vai:

1. Rodar `docker compose ps` — deve mostrar 4 containers rodando (`Up`)
2. Rodar `curl http://localhost:8080` — deve retornar JSON com `"status":"200"`
3. Te pedir pra abrir `http://SEU_IP:3000` no navegador — vai aparecer o Manager UI (tela azul com "Evolution Manager")

## Você vai precisar guardar

- **API key** que o Claude gerou (32 caracteres aleatórios)
- **URL da sua Evolution:** `http://SEU_IP:8080`
- **URL do Manager:** `http://SEU_IP:3000`

## Tempo esperado

~10-15 minutos, principalmente esperando o Docker baixar imagens.

## Deu erro?

Ver [troubleshooting/evolution-nao-inicia.md](../troubleshooting/evolution-nao-inicia.md).

Se o Claude não resolver, chama o Atilio na sala.
