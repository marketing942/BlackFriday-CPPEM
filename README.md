# Black Friday CPPEM — página de captura

Landing da live de Black Friday da CPPEM: **quarta, 04/11, às 19h45, ao vivo no YouTube**
([@cppemconcursos](https://www.youtube.com/@cppemconcursos)). A página capta a **lista VIP**
(nome, WhatsApp, e-mail) e leva o inscrito ao grupo do WhatsApp.

Página estática: `index.html` + `styles.css` + `script.js` + `public/`. Paleta prata e ouro
sobre grafite (sem vermelho), Anton + Montserrat.

## Antes de publicar

| O quê | Onde |
|---|---|
| ⚠ **Link do grupo do WhatsApp** — vazio, o inscrito vai para o canal do YouTube | `CONFIG.grupoWhatsApp` no `script.js` |
| Link do vídeo agendado da live (opcional: vira "Ativar lembrete") | `CONFIG.youtubeLive` |
| Aba da planilha (hoje `BLACK_FRIDAY`, criada sozinha pelo Apps Script) | `CONFIG.sheetAba` |
| `og:image` 1200×630 com URL absoluta para o preview no WhatsApp | `<head>` do `index.html` |
| Categorias dos cards "lacrados" (remova as que não entrarem) | seção `#lacrados` |

## Como a página se comporta

- **Abertura** (uma vez por sessão): tela preta → BLACK trinca o vidro → FRIDAY bate com raios →
  o núcleo carrega → explosão, o vidro estilhaça e o leão sai do meio. `?abertura=0` pula,
  `?abertura=1` força; botão "Pular" e `Esc` também. Respeita `prefers-reduced-motion`.
- **Fases automáticas** a partir de `CONFIG.inicio`: *antes* (contagem + formulário), *ao vivo*
  (por `CONFIG.duracaoHoras`, botões "Assistir ao vivo") e *depois* (gravação). Qualquer elemento
  com `data-fase-so="..."` só aparece na fase dele.
- **Pavio**: queima de `CONFIG.pavioInicio` até o início da live.
- **Prova**: comentários reais em `public/prova/` convertidos em "tinta" (texto escuro, fundo
  transparente) e impressos em bilhetes de papel rasgado, ouro e prata. Para trocar, gere a
  imagem do mesmo jeito e ajuste o `--w` do bilhete (largura em que o texto fica do tamanho dos outros).

## Medição

Lead no modo **site** (Modelo B, `TRACKING.md` §5): quem dispara é o `script.js` via
`pixel_x_app.send_event`; a barreira de submit corta a propagação. Não cadastre o id
`bf-cppem-submit` como conversão por clique na PixelX (§10.3).

Eventos no dataLayer: `cta_click`, `youtube_click`, `salvar_agenda`, `abertura_pulada`,
`inscricao_black_friday`.
