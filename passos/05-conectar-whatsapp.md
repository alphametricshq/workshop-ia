# Passo 05 — Conectar seu WhatsApp

> Voce faz manualmente no navegador. O Claude te guia.

## ANTES DE COMEÇAR — leia com atenção

O WhatsApp aceita **apenas uma sessão web ativa por vez**. Se você está logado em WhatsApp Web (navegador) ou WhatsApp Desktop (app), o Evolution não vai conseguir conectar.

**Desconecte TODAS as sessões agora:**

1. No seu **celular**, abre WhatsApp
2. Menu (3 pontinhos ou Configurações)
3. Clica em **Aparelhos conectados**
4. Se aparecer qualquer sessão de "Windows", "Mac" ou "Chrome", clica nela e **Desconectar**

Só depois disso segue.

---

## O que você vai fazer

Criar uma **instance** no Evolution (chame com seu nome/empresa), gerar um **QR code**, e escanear pelo celular.

## Passo a passo

### 1. Abrir o Manager

No navegador, vai em: **http://SEU_IP:3000** (troca `SEU_IP` pelo IP da sua VPS — aquele que a Contabo te mandou).

Vai aparecer a tela do **Evolution Manager** (fundo azul-escuro, logo "Evolution" no topo).

### 2. Fazer login no Manager

O Manager pede uma **API Key**. Cola aquela chave de 32 caracteres que o Claude gerou pra você no passo 04.

Clica em **Entrar** (ou **Login**).

### 3. Criar uma instance

Dentro do Manager, clica no botão **➕ Instance** (ou **New Instance / Nova Instância**) no canto superior direito.

Preenche:

- **Instance Name:** algo simples, tipo `atilio-workshop` (troca por seu nome)
- **Integration:** deixa **WHATSAPP-BAILEYS** (padrão)
- **Token:** deixa vazio (auto-gerado)

Clica em **Save** ou **Criar**.

### 4. Escanear o QR code

Apareceu um QR code grande na tela do Manager? Perfeito.

No seu **celular**:

1. Abre WhatsApp
2. **Configurações → Aparelhos conectados → Conectar aparelho**
3. Aponta a câmera do celular pro QR code na tela do computador

Em poucos segundos, o Manager vai mudar o status pra **CONNECTED** (verde). Seu WhatsApp está conectado à Evolution.

---

## Como saber que funcionou

- O card da instance no Manager mostra **status: open** (ou **CONNECTED**)
- Seu nome/foto aparece no card
- Se você rodar `curl http://SEU_IP:8080/instance/connect/atilio-workshop -H 'apikey: SUA_CHAVE'` — vai retornar JSON dizendo que está conectada

Volta pro Claude e diz "conectei". Ele avança pro momento eureka.

---

## ⚠️ Enquanto Evolution estiver conectado no seu número:

- **WhatsApp Web não funciona** no seu navegador
- **WhatsApp Desktop não funciona**
- **O WhatsApp do celular funciona normal** (é só uma sessão adicional)
- Se você precisar do WhatsApp Web depois, pode desligar a instance no Manager (botão **Logout**) e reconectar via Web normalmente

---

## Deu erro?

Ver [troubleshooting/whatsapp-web-conflito.md](../troubleshooting/whatsapp-web-conflito.md).

Se o QR code não aparecer, chama o Claude — ele reinicia a instance. Se não resolver, chama o Atilio.
