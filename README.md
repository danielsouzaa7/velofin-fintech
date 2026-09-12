# VeloFin — Tela de Acesso

**Gestão financeira para quem vive de renda variável.**
Interface de login do MVP acadêmico **VeloFin**, construída em HTML semântico, CSS e Tailwind CSS v4.

> Projeto acadêmico desenvolvido na **FIAP** (Análise e Desenvolvimento de Sistemas — 1TDS, Fase 4).
> Não é um produto em produção e não processa dados reais.

🔗 **Demo ao vivo:** https://danielsouzaa7.github.io/velofin-fintech/

---

## O problema

Vendedor comissionado não tem salário previsível. O dinheiro entra em blocos irregulares — uma semana forte seguida de três fracas — e a maioria das ferramentas de finanças pessoais assume renda fixa mensal. O resultado prático é conhecido: a pessoa gasta no ritmo do mês bom e aperta no mês ruim.

O **VeloFin** ataca esse problema com três mecanismos:

| Mecanismo | O que resolve |
|---|---|
| **Registro de vendas e comissões** | Calcula automaticamente o valor de cada comissão, em vez de planilha manual |
| **SmartBuffer** — reserva de segurança | Separa uma reserva sincronizada com o banco para atravessar os meses fracos |
| **Metas mensais com progresso** | Transforma o objetivo do mês em acompanhamento em tempo real |

**Para quem:** vendedores, representantes comerciais e autônomos com renda variável.

---

## O que eu fiz neste repositório

Este repositório entrega **a tela de acesso** — a porta de entrada do sistema. A partir das telas desenhadas na Fase 2 do projeto, eu:

- reconstruí a interface em **HTML semântico**, com `label`/`for` em todos os campos e estrutura navegável por teclado;
- montei o **design system da marca** em `src/input.css` usando a diretiva `@theme` do Tailwind v4 — tipografia, paleta (`vf-ink`, `vf-emerald`, `vf-mint`, `vf-gold`…) e tokens de superfície;
- implementei o layout **split-panel** responsivo: painel de marca à esquerda, formulário à direita, empilhando automaticamente no mobile;
- configurei o pipeline do **Tailwind CLI** (`build` minificado e `dev` com watch);
- mantive **zero CSS inline e zero `<style>`** — toda a estilização vem de `css/styles.css`.

---

## Stack

`HTML5` · `CSS3` · `Tailwind CSS v4 (Tailwind CLI)` · `npm`

Sem framework de JavaScript, sem dependência de runtime, sem build obrigatório para rodar.

---

## Estrutura

```
.
├── index.html        # a tela (HTML semântico)
├── css/
│   └── styles.css    # CSS compilado — é o que o navegador consome
├── src/
│   └── input.css     # fonte do Tailwind: tokens da marca via @theme
├── package.json
└── README.md
```

---

## Como rodar

O CSS já vem compilado, então **não é preciso instalar nada**:

```bash
git clone https://github.com/danielsouzaa7/velofin-fintech.git
cd velofin-fintech
# abra index.html no navegador (duplo clique) — funciona offline
```

Para editar os tokens da marca e recompilar:

```bash
npm install
npm run build   # gera css/styles.css minificado
npm run dev     # recompila em watch
```

---

## Decisões técnicas

- **CSS compilado versionado.** O arquivo `css/styles.css` vai para o repositório de propósito: quem clona precisa conseguir abrir a tela sem Node instalado. O custo é um artefato de build no controle de versão — aceito conscientemente porque o público deste projeto é avaliador acadêmico, não time de engenharia.
- **Tailwind v4 com `@theme` em vez de `tailwind.config.js`.** A v4 move a configuração para CSS; declarar os tokens da marca em `src/input.css` mantém identidade visual e estilos no mesmo lugar.
- **Sem JavaScript.** O escopo da Fase 4 é a interface. Adicionar validação simulada em JS daria aparência de funcionalidade que não existe — preferi uma tela honesta a uma tela que finge autenticar.
- **`novalidate` no formulário.** A validação nativa do navegador entraria em conflito com a validação real da fase seguinte; deixar explícito evita falso sinal de "já valida".
- **Semântica antes de estética.** `label`/`for`, `type` correto em cada input e hierarquia de headings — a tela é navegável por teclado e legível por leitor de tela.

---

## Status

**Concluído** para o escopo da Fase 4 (interface de acesso). Congelado — sem desenvolvimento ativo.

## Limitações — o que esta tela **não** faz

- Não autentica: o formulário não envia para lugar nenhum (`action="#"`).
- Não há back-end, banco de dados, sessão nem recuperação de senha.
- Não há validação de campos, cliente ou servidor.
- Os números exibidos no painel de marca (patrimônio, variação) são **ilustrativos**, fixos no HTML.
- Os selos "Conexão segura — SSL/TLS" e a menção à LGPD são **elementos de layout** da tela desenhada, não afirmações sobre uma implementação existente.

## Próximos passos

- Validação de formulário e estados de erro acessíveis
- Autenticação real com back-end e sessão
- Telas de cadastro, dashboard e registro de vendas
- Testes de acessibilidade automatizados

## Aprendizados

Traduzir uma tela de design para HTML expôs o quanto decisão de token de design é decisão de engenharia: definir a paleta em `@theme` uma vez eliminou dezenas de valores mágicos espalhados pelas classes. A outra lição foi de escopo — resistir a colocar JavaScript "só para parecer que funciona" tornou o projeto mais fácil de defender do que se ele simulasse um login.

---

## Licença

O `package.json` traz `"license": "MIT"`, mas o repositório **não possui arquivo `LICENSE`** e a titularidade de um trabalho acadêmico da FIAP ainda precisa ser confirmada. A decisão de licenciamento está **pendente** — não trate a menção no `package.json` como concessão formal de licença.

---

**Daniel Souza Valerio** — FIAP · Análise e Desenvolvimento de Sistemas
[linkedin.com/in/danielsouzavalerio](https://www.linkedin.com/in/danielsouzavalerio)
