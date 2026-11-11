# 🌙 Guia de Tarot

Site pessoal de estudo e registro de tiragens, com quatro baralhos: **Tarot** (78 cartas), **Baralho Cigano** (36 cartas, Montovanni), **Cigano Latim** (Petit Lenormand em latim, 39 cartas) e **Sibilla** (Sibilla Oracle Cards, 52 cartas).

🔗 **[Abrir o Guia](https://lumaminikel.github.io/tarot/)**

## Páginas

- **`index.html`** — Guia com as cartas de cada baralho (significados, palavras-chave, combinações e tiragens), busca por nome, número ou palavra de sentido parecido, e foto da carta em pop-up.
- **`diario-tarot.html`** — Diário de tiragens. Usa login (Firebase Authentication) e salva o histórico no Firestore, por usuário. Tem busca de cartas, calendário, revisão espaçada, leitura com IA (Gemini, com a sua chave) e painel de administração do conteúdo.
- **`perfil.html`** — Perfil: nome, chave da IA (Gemini) e dados de nascimento usados no mapa natal.

## Estrutura

| Arquivo / pasta | O que é |
| --- | --- |
| `tarot-cards.js` | Fonte única dos dados das cartas usados pelo diário (textos, palavras-chave e caminhos das imagens dos quatro baralhos) |
| `rider-waite/` | Imagens do Tarot (`Cups01.jpg`, `Wands01.jpg`, `RWS_Tarot_00_Fool.jpg`...) |
| `cigano/` | Imagens do Baralho Cigano (Montovanni) |
| `cigano_latim/` | Imagens do Cigano Latim (`00_O_Tolo.jpg`... `38_A_Cruz.jpg`) |
| `sibilla/` | Imagens do Sibilla, no formato `01_O_Amor.jpg` (os nomes estão em `SIBILLA_IMAGES` no `tarot-cards.js` e no `index.html`). Sem a foto, aparece o ícone 🃏 |
| `sw.js`, `manifest.json`, `icon-*.png` | Modo offline e instalação como app |

## Ao alterar o projeto

- **Mudou o `tarot-cards.js`?** Aumente o número em `tarot-cards.js?v=` no `diario-tarot.html` e no `sw.js` (e o `CACHE_VERSION` do `sw.js`), para o navegador não continuar usando a cópia antiga.
- **Mudou imagens com o mesmo nome?** Aumente o `CACHE_VERSION` do `sw.js`.
- O guia (`index.html`) tem os próprios mapas de imagens e o mapa de oráculo do Tarot, separados do `tarot-cards.js`.
