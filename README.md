# michielpostma-blocks

Statische HTML-blocks die via WordPress shortcode `[claude_block slug="..."]` in pagina's worden ingebed. Gehost op Netlify, ingebed door de `claude-blocks` WP-plugin op michielpostma.nl.

## Structuur

```
/blocks/
  _template.html           # Skeleton voor nieuwe blocks
  dockr-klantcase.html     # Voorbeeld klantcase
  ...
netlify.toml               # Build + headers config
index.html                 # Overview pagina
```

## Een nieuw block toevoegen

1. Kopieer `_template.html` naar `blocks/<nieuwe-slug>.html`
2. Vervang `{{slug}}` met de daadwerkelijke slug overal in het bestand
3. Vul content in
4. Commit + push naar `main`
5. Netlify deployt binnen ~30s

## CSS-strategie

Elke block:
- Wrapt alles in `<div class="cb-<slug>">`
- Heeft `all: revert` reset op container + descendants
- Prefixt élke selector met `.cb-<slug>`

## Block ophalen testen

```bash
curl https://michielpostma-blocks.netlify.app/blocks/dockr-klantcase.html
```
