# Evolution API nao esta iniciando

## Sintomas

- `docker compose up -d` roda mas quando voce acessa `http://SEU_IP:8080` nao carrega nada
- `docker compose ps` mostra algum container em status `Restarting` ou `Exit`
- Manager (`http://SEU_IP:3000`) abre a tela azul mas nao conecta na API

## Diagnostico rapido

Peca pro Claude rodar (via MCP da VPS):

```bash
cd /opt/evolution
docker compose ps
docker compose logs --tail 50 evolution_api
```

### Erro tipico 1: porta 8080 ja em uso

```
Error: bind: address already in use
```

Outra aplicacao esta usando a porta 8080. Solucao: pedir pro Claude mudar a porta pra 8090 no `docker-compose.yaml` (mapping `8090:8080`) e refazer `docker compose up -d`.

### Erro tipico 2: firewall bloqueando

A VPS pode ter firewall bloqueando as portas 8080 e 3000. Pedir pro Claude:

```bash
ufw allow 8080/tcp
ufw allow 3000/tcp
ufw reload
```

### Erro tipico 3: postgres nao subiu

Docker logs do postgres mostra erro. Geralmente eh permissao em `/var/lib/postgresql/data`. Solucao:

```bash
docker compose down -v
docker compose up -d
```

(o `-v` remove volumes — vai perder dados, mas em setup novo tudo bem)

### Erro tipico 4: image nao existe

A versao da imagem no docker-compose pode estar quebrada. Trocar `atendai/evolution-api:v2.2.3` por `atendai/evolution-api:latest` e refazer.

## Se nada resolver

O Claude nao consegue resolver? Chama o Atilio na sala. Este eh o passo mais tecnico do workshop — tem varios pontos de falha e alguns pedem intervencao manual.
