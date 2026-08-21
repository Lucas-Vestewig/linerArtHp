# Lineart HP — Landing Page (redesign)

Landing page redesenhada da Lineart HP (comunicação visual em grande formato, Blumenau/SC), pronta para publicar no GitHub e hospedar na Vercel.

## Sobre as imagens

O site original mudou de estrutura entre a primeira e a segunda análise (o caminho das imagens passou de `/wp-content/uploads/...` para `/assets/2026/07/...`). Por isso os primeiros links usados aqui davam erro 404 — não era bloqueio de hotlink, era caminho desatualizado.

Agora todas as imagens do portfólio, dos logos de clientes e da marca apontam **direto para o site oficial** (`https://linearthp.com/assets/2026/07/...`), exatamente como no protótipo original. A única imagem hospedada localmente neste projeto é a foto aérea da sede (`assets/img/sobre/empresa.jpeg`), que já é o arquivo real enviado por vocês.

> Importante: como essas imagens do portfólio/clientes/logo estão sendo carregadas diretamente do domínio `linearthp.com`, elas só aparecem enquanto esse site estiver no ar. Se um dia quiserem independência total do domínio antigo, é só baixar cada imagem e trocar o `src` pelo caminho local — a estrutura de pastas (`assets/img/`) já está pronta para isso.

## Estrutura do projeto

```
site/
├── index.html                  → versão clara (página inicial)
├── escuro.html                 → versão escura (fundo preto)
├── vercel.json                 → configuração de deploy da Vercel
├── package.json
├── assets/
│   └── img/
│       └── sobre/empresa.jpeg  → foto real da sede (única imagem local)
```

## Deploy na Vercel — Root Directory

Este projeto fica dentro da pasta `site/`. Se o `index.html` não estiver na raiz do seu repositório GitHub, configure isso uma vez na Vercel:

1. Dashboard da Vercel → seu projeto → **Settings → General**.
2. Campo **Root Directory** → clique em **Edit** → digite `site` → salve.
3. Vá em **Deployments** → abra o menu **⋯** do último deploy → **Redeploy**.

## Rodando localmente

```bash
npm run dev
```

Abre em `http://localhost:3000`. Também dá para abrir `index.html` direto no navegador.

## Publicando no GitHub

```bash
git init
git add .
git commit -m "Landing page Lineart HP - redesign"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/linerArtHp.git
git push -u origin main
```

## Acessando as duas versões

- Versão clara: `https://seu-projeto.vercel.app/`
- Versão escura: `https://seu-projeto.vercel.app/escuro` (fundo preto neutro, sem tom azulado)

## Avaliações do Google (sempre atualizadas)

No topo do `<script>` de `index.html` e `escuro.html` há duas variáveis (`GOOGLE_MAPS_API_KEY` e `GOOGLE_PLACE_ID`). Preenchendo as duas, a seção de avaliações passa a buscar nota, quantidade e comentários reais direto do Google a cada carregamento da página. As instruções de onde conseguir cada chave estão comentadas no próprio código.
