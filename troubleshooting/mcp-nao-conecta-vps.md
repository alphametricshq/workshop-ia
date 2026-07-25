# MCP da VPS nao consegue conectar

## Sintoma

O Claude tenta rodar um comando na VPS via MCP e retorna erro de conexao.

## Diagnostico rapido

### 1. IP correto?

Verifica se o IP no email da Contabo eh exatamente o mesmo que voce passou pro Claude. Nao confunde com o IP local do seu roteador (192.168.x.x nao serve).

### 2. Senha certa?

Copia a senha do email da Contabo com cuidado — as vezes tem espacos no comeco ou fim ao colar. Cole num editor de texto primeiro pra ver se tem espaco.

### 3. VPS esta online?

Abre um terminal (ou pede pro Claude fazer): `ping SEU_IP`

Se der "Request timed out", a VPS pode nao estar ativa ainda ou tem firewall bloqueando ping (nao eh problema).

### 4. Firewall do seu computador

Alguns computadores corporativos bloqueiam SSH (porta 22) na saida. Nesse caso, o MCP nao vai conectar. Tenta em outra rede (4G do celular) pra testar.

## Ainda travado?

Chama o Atilio. Este eh o passo mais tecnico do workshop — normal ter fricao aqui.
