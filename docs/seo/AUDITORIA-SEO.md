# Auditoria SEO — Black Friday CPPEM

Repositório: [`marketing942/BlackFriday-CPPEM`](https://github.com/marketing942/BlackFriday-CPPEM) · branch `seo/otimizacao-organica-20261023` (base `main`) · 23/10/2026
Relatório consolidado do ecossistema: [RELATORIO-GERAL-SEO-ECOSSISTEMA.md](RELATORIO-GERAL-SEO-ECOSSISTEMA.md)

## Arquitetura

- **Domínio de produção:** black-friday.cppem.com.br — evidência: informado pelo responsável em 23/10/2026.
- **Stack:** HTML + CSS + JavaScript estáticos (`framework: null`), assets em `assets/`. Fontes do Google (Anton, Montserrat, Share Tech Mono).
- **Renderização:** HTML estático; fases da campanha (antes/ao vivo/depois) trocadas por JavaScript a partir de `CONFIG.inicio`.

## Rotas

| Rota | O que é | Indexação |
|---|---|---|
| / | Lista VIP da live de Black Friday (04/11/2026, 19h07, YouTube) | Indexar durante a campanha |

## Finalidade e classificação

- **Objetivo:** Capturar inscrições (nome, WhatsApp, e-mail) para a live de Black Friday e levar ao grupo do WhatsApp.
- **Unidade de negócio:** CPPEM Concursos
- **Público:** Base e interessados em mentorias, materiais e cursos CPPEM.
- **Tipo de página:** Campanha temporária / captura.
- **Indexação recomendada:** Indexar enquanto a campanha estiver ativa. Depois da live: manter com a gravação ou redirecionar — decisão de negócio (ver estratégia).
- **Potencial orgânico:** **Baixo** — Demanda praticamente só de marca ("black friday CPPEM") e janela de dias. Termos genéricos ("black friday cursos concurso") são de grandes players e notícias.

## Problemas encontrados

Gravidade: **P0** crítico (indexação/integridade) · **P1** alto impacto · **P2** médio · **P3** evolução · **Info** registro sem ação de SEO.

| Sev. | Problema | Evidência | Impacto | Status |
|---|---|---|---|---|
| P1 | Sem canonical, og:url e og:image absolutos | O README já listava a og:image 1200×630 como pendência | Preview sem imagem e duplicação com `*.vercel.app` | Corrigido (domínio black-friday.cppem.com.br; imagem recortada de leao-fundo.webp) |
| P2 | Title sem o ano | `Black Friday CPPEM · 04/11 às 19h07, ao vivo no YouTube` | Buscas sazonais costumam incluir o ano | Corrigido |
| P2 | Description com 232 caracteres |  | Corte | Corrigido (146) |
| P2 | Sem dados estruturados |  |  | Corrigido (WebPage + Organization). Sem `Event` de propósito |
| P2 | Sem robots.txt e sitemap |  |  | Corrigido |
| P3 | URL de campanha nova a cada ano | Repositório/URL dedicados à edição | Autoridade não acumula entre edições | Recomendado (URL perene) |

## Limitações desta auditoria

- **Produção inacessível desta sessão.** O proxy de rede do ambiente recusou
  conexões a `*.cppem.com.br` e `*.vercel.app`, e o leitor de páginas não
  resolveu esses domínios. Nada foi medido no site publicado: HTML servido,
  status HTTP, redirecionamentos e headers reais ficam **não validados**.
  Toda a auditoria foi feita no código e em servidores locais.
- **Sem Google Search Console, GA4, Keyword Planner, Trends, Semrush ou Ahrefs.**
  Não há volume, dificuldade, CPC nem posição. Nenhum número desse tipo
  aparece aqui. As prioridades de palavra-chave são **estimativas
  qualitativas** (intenção, tipo de página que aparece hoje, relevância
  comercial) e devem ser confirmadas no Search Console e no Planejador.
- **SERP observada com a busca web disponível, que não é o Google.** Os
  concorrentes listados são os que apareceram nessa busca e servem como
  indício, não como ranking do Google.
- **Lighthouse é dado de laboratório**, rodado localmente com os terceiros
  (GTM, PixelX, fontes do Google) bloqueados. Serve para comparar antes ×
  depois, não para prever o Core Web Vitals real (dado de campo do CrUX).
