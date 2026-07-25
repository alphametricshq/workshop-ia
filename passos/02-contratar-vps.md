# Passo 02 — Contratar VPS Contabo

> Conduzido pelo Claude.

## O que vamos fazer

Contratar um servidor Linux na nuvem — VPS Contabo. Custa ~R$50/mes (8 euros). Vai ficar ligado 24/7 e vai rodar sua Evolution API (WhatsApp).

## Passo a passo

### 1. Abrir o site

No navegador, vai em: **https://contabo.com/en/vps/**

### 2. Escolher o plano

Escolhe o plano mais basico da lista — geralmente **VPS 10 SSD**. Tem:
- 4 vCPU cores
- 6 GB RAM
- 100 GB NVMe SSD
- ~R$45/mes

Clica em **Configure**.

### 3. Configurar

Na tela de configuracao:

- **Region:** European Union (ou US East, se quiser)
- **Storage type:** SSD (padrao)
- **Contract period:** 1 mes (nao commit longo)
- **Operating system:** **Ubuntu 24.04** (importante — Linux amigavel)
- **Login and password:** define uma senha forte pra root. **Anota essa senha — voce vai precisar depois.**

Depois clica em **Continue**.

### 4. Pagamento

Cria conta com seu email. Preenche endereco (pode ser o da sua empresa). Escolhe cartao de credito internacional.

### 5. Aguardar ativacao

Apos o pagamento, a Contabo demora entre 5 minutos e algumas horas pra ativar. Voce vai receber um email quando o servidor estiver pronto — com o **IP** do servidor e a **senha** que voce definiu.

**Enquanto espera:** volta pro Claude, ele te ajuda com os proximos passos.

## Anota isto:

- **IP da VPS:** _____________ (vem no email da Contabo)
- **Senha root:** _____________ (a que voce escolheu)

Voce vai colar esses dois valores em breve.
