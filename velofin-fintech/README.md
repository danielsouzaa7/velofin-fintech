# VeloFin — Tela de Login

**Gestão financeira inteligente para vendedores comissionados.**

Tela de **acesso/login** do projeto Fintech **VeloFin**, recriada em HTML, CSS e
**Tailwind CSS** a partir das telas desenhadas na Fase 2.

> _"Controle seu dinheiro antes que ele controle você."_

---

## Sobre o projeto

O **VeloFin** é um MVP de gestão financeira voltado para vendedores que trabalham
por comissão. Esta tela é a porta de entrada do sistema e apresenta:

- **Registro de vendas e comissões** — cálculo automático do valor de cada comissão.
- **SmartBuffer** — reserva de segurança sincronizada com o banco.
- **Metas mensais com progresso** — acompanhamento em tempo real.

A interface usa um layout **split-panel**: painel de marca à esquerda e o
formulário de acesso à direita. Em telas menores, o layout **empilha
automaticamente** (responsivo para mobile).

---

## Como abrir

Basta abrir o arquivo **`index.html`** no navegador (duplo clique).
O CSS já vem **compilado** em `css/styles.css`, então **funciona offline**, sem
necessidade de internet ou de qualquer build.

---

## Estrutura

```
velofin-fintech/
├── index.html          ← a tela (HTML semântico)
├── css/
│   └── styles.css       ← CSS já compilado pelo Tailwind (é o que o navegador usa)
├── src/
│   └── input.css        ← fonte do Tailwind (tokens da marca + @theme)
├── package.json
└── README.md
```

> O HTML está **separado** do CSS: nenhuma regra de estilo inline ou em `<style>`.
> Toda a estilização vem do arquivo `css/styles.css`.

---

## Recompilar o Tailwind (opcional)

Caso edite `src/input.css` e queira gerar o CSS novamente:

```bash
npm install
npm run build        # gera css/styles.css minificado
# ou, para desenvolver com recompilação automática:
npm run dev
```

Tecnologias: **HTML5 · Tailwind CSS v4 (Tailwind CLI) · CSS**

---

_FIAP — 1TDS · Fase 4 · Atividade: telas do Fintech (VeloFin)._
