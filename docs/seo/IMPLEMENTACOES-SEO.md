# Implementações de SEO — Black Friday CPPEM

Repositório: [`marketing942/BlackFriday-CPPEM`](https://github.com/marketing942/BlackFriday-CPPEM) · branch `seo/otimizacao-organica-20261023` (base `main`) · 23/10/2026
Relatório consolidado do ecossistema: [RELATORIO-GERAL-SEO-ECOSSISTEMA.md](RELATORIO-GERAL-SEO-ECOSSISTEMA.md)

Commits na branch `seo/otimizacao-organica-20261023`. Nada foi publicado; merge e deploy dependem de aprovação.

## Arquivos modificados

| Arquivo | Alteração | Por quê |
|---|---|---|
| index.html (`<head>`) | Title com 2026, description, robots e JSON-LD WebPage/Organization |  |
| robots.txt (novo) | Bloqueia `/docs/` e `/README.md` |  |
| .vercelignore (novo) | `docs/seo/` |  |

## Metadados — antes × depois

Extraídos do HTML renderizado localmente (Playwright/HTTP), antes e depois.

| Campo | Antes | Depois |
|---|---|---|
| `title` | Black Friday CPPEM · 04/11 às 19h07, ao vivo no YouTube | Black Friday CPPEM 2026 · Live 04/11 às 19h07 no YouTube |
| `description` | Black Friday CPPEM: uma live só, quarta-feira, 04/11, às 19h07, no YouTube da CPPEM. Os descontos do ano em mentorias, materiais e cursos são revelados ao vivo. Entre na lista VIP e receba o lembrete no WhatsApp. | Black Friday CPPEM 2026: live no YouTube na quarta, 04/11, às 19h07, com os descontos do ano em mentorias, materiais e cursos. Entre na lista VIP. |
| `canonical` | — | https://black-friday.cppem.com.br/ |
| `robots` | — | index, follow, max-image-preview:large |
| `og:image` | — | https://black-friday.cppem.com.br/assets/og-black-friday.jpg |
| `og:url` | — | https://black-friday.cppem.com.br/ |
| JSON-LD |  | WebPage |

## Dados estruturados

Só tipos aplicáveis e só com dados que a página mostra. Nada de avaliações,
preços inventados, prêmios ou credenciais. Sem `FAQPage` (o resultado de FAQ
foi restrito a sites de governo e saúde em 2023 — [Google — Mudanças nos resultados de FAQ/HowTo (2023)](https://developers.google.com/search/blog/2023/08/howto-faq-changes) — e o
changelog da documentação registra a descontinuação em 2026 — [Google — Atualizações da documentação da Pesquisa (changelog)](https://developers.google.com/search/updates)) e sem `Course`
(o Course Info saiu dos resultados em 2025: [Google — Simplificação da página de resultados (Course Info descontinuado, 2025)](https://developers.google.com/search/blog/2025/06/simplifying-search-results)). Sem promessa
de resultado enriquecido.

## Benefícios esperados

- Título e descrição alinhados à intenção principal → mais impressões
  relevantes e CTR (a confirmar no Search Console).
- Canonical absoluto → sinais concentrados no domínio de produção
  ([Google — Como especificar uma URL canônica](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls)).
- `WebSite` com `name` no subdomínio → chance de o Google exibir o nome do site
  em vez do host ([Google — Nomes de sites na Pesquisa (subdomínios)](https://developers.google.com/search/docs/appearance/site-names)).
- Preview correto no WhatsApp/redes (tráfego de compartilhamento).
