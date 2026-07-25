# Passo 03 — Dar acesso da VPS pro Claude

> Conduzido pelo Claude. Voce so cola IP + senha uma vez.

## O que voce precisa em maos

1. **Email do Contabo** — procure na sua caixa de entrada:
   - **De:** `no-reply@contabo.com`
   - **Assunto:** "Your login data" (ou similar em ingles)
   - Se nao encontrar, verifica o **spam** — email da Contabo pode cair la

2. **Extrai do email:**
   - **IP address** (algo tipo `85.239.235.168`)
   - **user name** (sempre `root` pra Contabo)

3. **Da sua memoria/anotacao:**
   - **Senha root** — a que VOCE escolheu na contratacao (passo 02). **O email NAO envia senha nova** — ele apenas diz "as chosen by you during order process", ou seja, e a mesma que voce criou.

Se voce esqueceu a senha, ver secao "Como recuperar senha" no fim deste arquivo.

---

## Como funciona

O Claude Code tem um **terminal integrado** — aquele que aparece embaixo da aba Code. Por esse terminal, o Claude pode se conectar na sua VPS via SSH (a forma padrao de acessar servidor Linux remotamente).

**Voce nao precisa:**

- Instalar Termius, PuTTY, ou nenhum programa de SSH
- Abrir a VPS voce mesmo
- Ver o Ubuntu, ver a tela do servidor, nem saber que Linux existe
- Rodar nenhum comando no seu computador manualmente

**O Claude faz tudo pelo terminal integrado.** Voce so aprova quando ele pedir.

---

## O que o Claude vai fazer

### 1. Pedir seu IP e senha

Cola:

- **IP** (do email da Contabo)
- **Senha** (a que voce criou na contratacao)

Sem espacos extras no comeco/fim.

### 2. Testar conexao SSH

O Claude vai rodar (no terminal integrado dele):

```bash
ssh -o StrictHostKeyChecking=no root@SEU_IP
```

Na primeira vez, o Linux pergunta a senha. O Claude vai colar automaticamente (via `sshpass` no Mac/Linux ou `plink` no Windows). Se conectar com sucesso, aparece o terminal do Ubuntu — e o Claude sai imediatamente (`exit`) pra confirmar que funciona.

### 3. Gerar chave SSH pra nao precisar de senha toda hora

O Claude gera um par de chaves no seu computador:

```bash
ssh-keygen -t ed25519 -f ~/.ssh/vps_workshop -N ""
```

E copia a chave publica pra sua VPS:

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

> "Perfeito! Sua VPS respondeu. Estou conectado via SSH sem precisar de senha. Agora vou continuar com o proximo passo — instalar Evolution API."

Voce nao precisa ver nenhuma tela de Linux. Nem precisa saber SSH e sigla de que (Secure SHell, se voce tiver curiosidade). O Claude cuida.

---

## Como recuperar senha da VPS (se voce esqueceu)

1. Login em [contabo.com](https://contabo.com)
2. **Your Services** → clica na sua VPS
3. Botao **Password Reset** (ou similar) — vai gerar nova senha e mandar por email
4. Aguarda o novo email da Contabo com a senha atualizada
5. Volta pro Claude com a nova senha

---

## Se der outro erro

Ver [troubleshooting/ssh-nao-conecta.md](../troubleshooting/ssh-nao-conecta.md).

Os 3 problemas mais comuns:

1. **IP ou senha errada** — conferir com o email original da Contabo (IP) e sua anotacao (senha)
2. **VPS ainda nao ativou** — aguardar mais alguns minutos
3. **Sua rede bloqueia porta 22** — raro, mas alguns wifi corporativos bloqueiam. Fallback: usar 4G do celular

Se travar de vez, chama o Atilio na sala.

---

## Detalhe tecnico (opcional — pra sua cultura geral)

O que voce acabou de configurar se chama **acesso SSH com chave publica/privada**. E o padrao profissional pra acessar servidores. Voce nunca mais vai precisar digitar a senha da VPS — a chave privada no seu computador e sua identidade.

Se voce trocar de computador, vai precisar copiar a pasta `~/.ssh/` pro novo, ou repetir esse passo. O Claude te ajuda em qualquer maquina.
