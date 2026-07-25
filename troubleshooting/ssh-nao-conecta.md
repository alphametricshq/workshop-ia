# SSH não conecta na VPS

## Sintoma

O Claude tenta `ssh root@SEU_IP` e recebe um dos erros:

- `Connection timed out`
- `Permission denied (publickey,password)`
- `Connection refused`
- `Host key verification failed`

## Diagnóstico

### Erro: `Connection timed out`

A VPS não está respondendo na porta SSH (22).

**Possibilidades:**

1. **VPS ainda não ativou** — espera mais 5-10 minutos, tenta de novo
2. **IP errado** — confere no painel da Contabo (contabo.com → Login → Your Services). O IP correto está listado ali.
3. **Sua rede bloqueia SSH** — alguns wifi corporativos ou redes de hotel bloqueiam porta 22. **Fallback:** conectar seu notebook no 4G do celular (hotspot) e tentar de novo.

### Erro: `Permission denied`

A senha está errada ou o usuário está errado.

- **Verifica a senha** — copia direto do email da Contabo, sem espaços no começo/fim
- **Verifica o usuário** — tem que ser `root` (não `admin`, não o teu nome)

### Erro: `Connection refused`

A VPS está online mas SSH não está rodando. É raro no Contabo padrão. Solução: reiniciar a VPS pelo painel Contabo (botão **Reboot**).

### Erro: `Host key verification failed`

Seu computador já tem um registro antigo de outra VPS com esse mesmo IP. Solução (o Claude faz):

```bash
ssh-keygen -R SEU_IP
```

Depois tenta conectar de novo.

---

## Como recuperar senha da VPS

Se você esqueceu a senha que você definiu na Contabo:

1. Login em [contabo.com](https://contabo.com)
2. **Your Services** → clica na sua VPS
3. Botão **Password Reset** — vai gerar nova senha e mandar por email

---

## Se nada resolver

Chama o Atilio na sala. Este é o passo mais dependente da rede/Contabo — varia bastante entre notebooks.
