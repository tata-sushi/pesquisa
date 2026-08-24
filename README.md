# Pesquisa — TATÁ Sushi

Repositório que **hospeda a página da pesquisa (survey)** para disparo. A ideia é simples: uma página HTML estática, publicada em um link limpo, que pode ser enviada (disparada) para as pessoas responderem.

- **URL do disparo:** https://pesquisa.tatasushi.tech
- **Hospedagem:** GitHub Pages (site estático, mesmo padrão do repositório `lideres`)

---

## Como funciona

A pesquisa é servida na **raiz** do domínio, ou seja, o arquivo [`index.html`](./index.html) é a própria página da pesquisa. O que está publicado hoje é uma **página de espera** ("Em breve") — ela deve ser substituída pelo HTML final da pesquisa.

Arquivos de configuração do GitHub Pages:

| Arquivo | Função |
|---|---|
| `index.html` | A página da pesquisa (hoje é a página de espera). |
| `CNAME` | Define o domínio próprio `pesquisa.tatasushi.tech`. |
| `.nojekyll` | Desliga o processamento Jekyll, publicando os arquivos como estão. |

---

## Como publicar / atualizar a pesquisa

1. Substitua o conteúdo de **`index.html`** pelo HTML da pesquisa.
2. Commit + push na branch **`main`**.
3. O GitHub Pages publica automaticamente em alguns instantes.

> O link do disparo é sempre a raiz: `https://pesquisa.tatasushi.tech/`. Mantendo a pesquisa em `index.html`, o link nunca muda.

---

## Setup inicial (uma vez só)

Depois do primeiro push, é preciso ligar o GitHub Pages e o domínio:

1. **Ligar o Pages:** repositório → **Settings → Pages** → *Source*: **Deploy from a branch** → *Branch*: **`main`** / **`/ (root)`** → **Save**.
2. **DNS do domínio:** no provedor onde `tatasushi.tech` está hospedado, criar um registro:
   - Tipo: **CNAME**
   - Nome/Host: **`pesquisa`**
   - Valor/Aponta para: **`tata-sushi.github.io`**
3. Aguardar a propagação do DNS e a emissão do certificado HTTPS (o GitHub faz isso sozinho; pode levar de alguns minutos a algumas horas).

> É o mesmo esquema já usado em `lideres.tatasushi.tech` — só muda o subdomínio.

---

## Respostas da pesquisa

A coleta/armazenamento das respostas é tratada pelo **formulário da pesquisa** (feito à parte). Este repositório cuida apenas da **hospedagem** da página. Quando a estratégia de respostas estiver definida (ex.: Supabase, como no `lideres`, ou um webhook), ela entra no próprio HTML da pesquisa.

---

## Identidade visual (para manter o padrão TATÁ)

Referência de estilo usada nas páginas da TATÁ, caso a pesquisa precise seguir o mesmo visual:

- **Fontes:** `DM Sans` (texto) e `DM Mono` (rótulos/mono) — via Google Fonts.
- **Cores (tokens CSS):**

```css
:root {
  --carbon:#35383F;  /* base escura / marca */
  --citric:#CFFF00;  /* destaque (verde-limão) */
  --bg:#F4F4F4;      /* fundo */
  --white:#FFFFFF;   /* cartões */
  --border:#E2E2E2;  /* bordas */
  --t1:#111111;      /* texto principal */
  --t2:#555555;      /* texto secundário */
  --t3:#999999;      /* texto terciário */
  --r:6px;           /* raio de borda */
}
```
