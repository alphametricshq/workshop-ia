# Passo 02 — Contratar VPS Contabo

> Conduzido pelo Claude.

## O que vamos fazer

Contratar um servidor Linux na nuvem — VPS Contabo. Custa ~R$50/mês (8 euros). Vai ficar ligado 24/7 e vai rodar sua Evolution API (WhatsApp).

## Passo a passo

### 1. Abrir o site

No navegador, vai em: **https://contabo.com/en/vps/**

### 2. Escolher o plano

Escolhe o plano mais basico da lista — geralmente **VPS 10 SSD** (Cloud VPS 10 tambem serve). Tem:

- 4 vCPU cores
- 6 GB RAM
- 100 GB NVMe SSD
- ~R$45/mes

Clica em **Configure**.

### 3. Configurar

Na tela de configuracao:

- **Region:** European Union (menor latencia da Europa; ou US East se preferir)
- **Storage type:** SSD (padrao)
- **Contract period:** 1 mes (sem commit longo)
- **Operating system:** **Ubuntu 24.04** (importante — Linux amigavel)

### 4. ⚠️ DEFINIR SENHA — leia com atencao

O Contabo te pede pra criar uma **senha root** agora. Essa senha:

- **Nao vem por email depois.** O email de confirmacao NAO vai te mandar senha nova — vai dizer literalmente "as chosen by you during order process" (a que voce escolheu na contratacao).
- **Voce vai precisar dela em 30 minutos** pra conectar na VPS.

**FACA AGORA:** anota essa senha em um lugar seguro. Papel, bloco de notas, gerenciador de senha — onde for. **Nao decore, ANOTE.**

Dica pra criar senha boa e memorizavel: mistura 2-3 palavras + 2-3 numeros + 1 simbolo. Ex: `alphaMetrics2026!` (mas NAO usa essa, cria a sua).

Depois clica em **Continue**.

### 5. Pagamento

Cria conta com seu email. Preenche endereco (pode ser o da sua empresa). Escolhe cartao de credito internacional.

### 6. Aguardar ativacao

Apos o pagamento, a Contabo demora entre 5 minutos e algumas horas pra ativar o servidor. Voce vai receber um **email de confirmacao** com:

- **De:** `no-reply@contabo.com`
- **Assunto:** "Your login data" (ou similar em ingles)
- **Conteudo:** tabela com IP address, user name (root), e outros dados

O email confirma **o IP da sua VPS** — anota tambem.

**Enquanto espera o email:** volta pro Claude, ele te ajuda com o passo seguinte.

---

## O que voce vai ter no final

- **IP da VPS:** _____________ (vira no email da Contabo, ex: `85.239.235.168`)
- **Usuario:** `root` (padrao Contabo)
- **Senha:** _____________ (a que voce escolheu no passo 4 acima)

Esses 3 valores voce vai passar pro Claude no proximo passo.

---

## Deu erro?

Ver [troubleshooting/contabo-nao-ativa.md](../troubleshooting/contabo-nao-ativa.md) e [troubleshooting/cartao-recusou.md](../troubleshooting/cartao-recusou.md).
