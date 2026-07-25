# Passo 03 — Dar acesso da VPS pro Claude

> Conduzido pelo Claude. Você só cola IP + senha uma vez.

## O que você precisa em mãos

O email que a Contabo te enviou. Ele tem:

- **IP** da sua VPS (algo tipo `195.201.42.98`)
- **Senha root** (a que você definiu na hora da contratação)

Se você não recebeu o email ainda, aguarda — pode demorar até 30 minutos. Enquanto isso, avisa o Claude que você tá esperando.

---

## Como funciona

O Claude Code tem um **terminal integrado** — aquele que aparece embaixo da aba Code. Por esse terminal, o Claude pode se conectar na sua VPS via SSH (a forma padrão de acessar servidor Linux remotamente).

**Você não precisa:**
- Instalar Termius, PuTTY, ou nenhum programa de SSH
- Abrir a VPS você mesmo
- Ver o Ubuntu, ver a tela do servidor, nem saber que Linux existe
- Rodar nenhum comando no seu computador manualmente

**O Claude faz tudo pelo terminal integrado.** Você só aprova quando ele pedir.

---

## O que o Claude vai fazer (você só cola IP + senha uma vez)

### 1. Pedir seu IP e senha

Cola exatamente o que veio no email da Contabo. Sem espaços extras.

### 2. Testar conexão SSH

O Claude vai rodar (no terminal integrado dele):

```bash
ssh -o StrictHostKeyChecking=no root@SEU_IP
```

Na primeira vez, o Linux pergunta a senha. O Claude vai colar automaticamente (via `sshpass` no Mac/Linux ou `plink` no Windows). Se conectar com sucesso, vai aparecer uma tela do Ubuntu — e o Claude sai dela imediatamente (comando `exit`).

### 3. Gerar chave SSH pra não precisar de senha toda hora

O Claude gera um par de chaves no seu computador:

```bash
ssh-keygen -t ed25519 -f ~/.ssh/vps_workshop -N ""
```

E copia a chave pública pra sua VPS:

```bash
ssh-copy-id -i ~/.ssh/vps_workshop.pub root@SEU_IP
```

A partir daqui, o Claude conecta na VPS sem pedir senha. Cada comando vira:

```bash
ssh -i ~/.ssh/vps_workshop root@SEU_IP "comando aqui"
```

### 4. Testar que tudo funciona

O Claude roda um comando de teste:

```bash
ssh -i ~/.ssh/vps_workshop root@SEU_IP "hostname && whoami"
```

Se aparecer o nome do seu servidor + `root`, funcionou. **A partir daqui, o Claude controla sua VPS totalmente.**

---

## Como saber que funcionou

O Claude vai te dizer algo como:

> "Perfeito! Sua VPS respondeu. Estou conectado via SSH sem precisar de senha. Agora vou continuar com o próximo passo — instalar Evolution API."

Você não precisa ver nenhuma tela de Linux. Nem precisa saber SSH é sigla de quê (Secure SHell, se você tiver curiosidade). O Claude cuida.

---

## Se der erro

Ver [troubleshooting/ssh-nao-conecta.md](../troubleshooting/ssh-nao-conecta.md).

Os 3 problemas mais comuns:

1. **IP ou senha errada** — conferir com o email original da Contabo
2. **VPS ainda não ativou** — aguardar mais alguns minutos
3. **Sua rede bloqueia porta 22** — raro, mas alguns wifi corporativos bloqueiam. Fallback: usar 4G do celular

Se travar de vez, chama o Atilio na sala.

---

## Detalhe técnico (opcional — pra sua cultura geral)

O que você acabou de configurar se chama **acesso SSH com chave pública/privada**. É o padrão profissional pra acessar servidores. Você nunca mais vai precisar digitar a senha da VPS — a chave privada no seu computador é sua identidade.

Se você trocar de computador, vai precisar copiar a pasta `~/.ssh/` pro novo, ou repetir esse passo. O Claude te ajuda em qualquer máquina.
