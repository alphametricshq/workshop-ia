# Passo 06 — Momento Eureka

> **Última parte.** Você está prestes a enviar uma mensagem no WhatsApp usando um agente de IA que **você mesmo montou**.

---

## O que você vai fazer

Pedir pro seu Claude enviar uma mensagem no WhatsApp do **Atilio Amaral** (palestrante) — provando que sua Evolution API na sua VPS funciona de ponta a ponta.

**Número destino:** `+55 11 96191-6621` (Atilio)

---

## O prompt pra colar no Claude

```
Usa a Evolution API que a gente configurou na minha VPS pra enviar
uma mensagem no WhatsApp.

Destino: +5511961916621 (formato E.164, sem espacos/tracos, com 55 na frente)
Instance: [nome que voce criou no passo 05, ex: atilio-workshop]
Texto:
"Atilio, cheguei! Sou [SEU NOME] da [SUA EMPRESA] —
Alphametrics ligado pelo meu Claude. Deu certo aqui!"

Substitui SEU NOME e SUA EMPRESA pelos seus.
Usa o endpoint POST /message/sendText/[instance] com header apikey.
```

---

## O que vai acontecer

Em poucos segundos, sua mensagem vai chegar no WhatsApp do Atilio. Ele vai reagir/responder na hora.

Se outros empresarios ao seu lado tambem terminarem, uma cascata de mensagens vai chegar no celular do Atilio. Ele vai comentar em voz alta pra sala: **"Chegou o do fulano! Chegou o do beltrano!"** — e você vai ver que **funcionou de verdade**.

---

## Você conseguiu.

**Antes:** você não tinha nada.
**Agora:** VPS propria, Evolution rodando, WhatsApp conectado, e uma mensagem real enviada pelo seu Claude.

De absoluto zero pra um agente de IA funcional no seu negocio. Em ~2 horas.

---

## E se der errado?

### "Instance not connected"

Sua instance desconectou. Volta ao Manager (`http://SEU_IP:3000`), reconecta escaneando QR code de novo. Depois volta pro Claude.

### "Number not registered on WhatsApp"

Erro de formato do numero. Deve ser `5511961916621` (13 digitos, começando com 55, sem `+`, sem espaços, sem traços).

### "apikey invalid"

Verifica se o Claude está usando a API key certa — aquela que ele gerou no passo 04. Cola de novo.

### Se travar de vez

Chama o Atilio na sala. Ele destrava.

---

## O que vem depois?

- **Bonus 1:** [criar seu primeiro site na Vercel](07-criar-site-vercel.md)
- **Bonus 2:** [explorar a aba Cowork](08-explorar-cowork.md)
- **Longo prazo:** falar com a Alphametrics sobre acompanhamento pro seu time.
