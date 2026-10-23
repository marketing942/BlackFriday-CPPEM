# Auditoria de tracking — Black Friday CPPEM

Repositório: [`marketing942/BlackFriday-CPPEM`](https://github.com/marketing942/BlackFriday-CPPEM) · branch `seo/otimizacao-organica-20261023` (base `main`) · 23/10/2026
Relatório consolidado do ecossistema: [RELATORIO-GERAL-SEO-ECOSSISTEMA.md](RELATORIO-GERAL-SEO-ECOSSISTEMA.md)

Regra seguida: nenhum ID, evento, parâmetro, script, seletor, endpoint, UTM ou
regra de consentimento foi alterado. Nenhum token ou credencial aparece aqui.

## Inventário

| Integração | Onde | Detalhe |
|---|---|---|
| GTM server-side (loader first-party) | `index.html`, 1º script do `<head>` | `https://sgtm.cppem.com.br/metrics/` — o ID do container está no path; mesmo container das demais landings |
| GTM noscript | `index.html`, `<body>` | `https://sgtm.cppem.com.br/ns.html?id=GTM-PJ379FLQ` |
| PixelX | carregada pelo GTM (`pxa.cppem.com.br`) | máscara de telefone `.pxa_mask_phone`; o Lead é a regra do painel vinculada ao `id` do `<form>` |
| Formulário | `form#bf-cppem-form` (name `lead_form`) | Lead no modo site: o `script.js` chama `pixel_x_app.send_event` |
| Planilha de leads | POST no Apps Script | email, live, nome, pagina_url, telefone, utm_campaign, utm_content, utm_medium, utm_source |
| Eventos dataLayer (README) | `script.js` | `cta_click`, `youtube_click`, `salvar_agenda`, `abertura_pulada`, `inscricao_black_friday` |
| Grupo | `CONFIG` | `links.cppem.com.br/grupo-bf26` |

## Antes × depois

- Arquivos de tracking/fluxo (`script.js`, `styles.css`, `vercel.json`): **sem nenhuma alteração** (`git diff` vazio).
- Mudanças só em `<head>` (metadados/JSON-LD), arquivos novos (robots, sitemap,
  imagens OG) e imagens otimizadas com o mesmo nome.
- Resultado dos testes de execução: ver [RELATORIO-DE-TESTES.md](RELATORIO-DE-TESTES.md).

## Classificação

- GTM loader, noscript, dataLayer, formulários, campos enviados à planilha,
  UTMs e redirecionamentos: **validado por teste de execução** (antes × depois idênticos).
- Lead da PixelX / conversões no Meta e no GTM server-side: **não validado por falta de acesso**.

## Riscos remanescentes

- Nenhum risco novo.
