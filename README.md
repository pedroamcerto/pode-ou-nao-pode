# Pode ou Não Pode? — Célula Aquila

Jogo de cartas pra dinâmica de célula. Aparece uma situação do dia a dia, cada pessoa vota no próprio celular se **pode** ou **não pode**, o líder revela a resposta com explicação e versículos, e o grupo conversa.

- 3 a 20 pessoas, cada uma no seu celular. O celular do líder é a "sala".
- Votos anônimos: aparece quem votou, nunca o quê.
- Um único `index.html`, sem backend e sem build. Multiplayer direto entre os aparelhos (PeerJS/WebRTC).

## Como jogar

1. O líder abre o site, coloca o nome e toca em **CRIAR SALA**.
2. A galera escaneia o QR code ou digita o código de 4 letras.
3. O líder escolhe quantas cartas jogar (10, 20, 30, 40 ou todas) e toca em **COMEÇAR**.
4. Depois de revelar, toca nos versículos pra ler o texto (Almeida, domínio público) ou abrir na NVI.

O celular do líder precisa ficar com a tela aberta: se ele fechar, a sala cai.

## Editar as cartas

As cartas ficam no array `DECK`, no topo do `<script>` do `index.html`:

```js
{ q:"Situação", a:true, tag:"Pode (e deve)", exp:"Explicação", ref:"Ef 4:26-27 · Mt 5:9", conversa:"Pergunta pra conversar" }
```

- `a: true` = PODE (verde), `a: false` = NÃO PODE (vermelho), `a: null` = DEPENDE (amarelo, pra temas em que cristãos sinceros divergem).
- `tag` é opcional e substitui o texto da faixa.
- `ref` usa abreviações em português separadas por ` · ` (ex.: `1Co 10:23-31`, `Sl 13`, `Jd 22`).

## Deploy

Site estático: a Vercel serve o `index.html` da raiz, sem build. Cada push na `main` publica de novo.

Pra testar localmente:

```bash
npx serve .
```
