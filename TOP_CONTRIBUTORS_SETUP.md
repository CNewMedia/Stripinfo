# Maandelijkse top bijdragers — installatie

De widget "Maandelijkse top bijdragers" wordt gevuld via de Discourse API. Als de inline-scriptversie niet werkt (bijv. door Ember SPA-navigatie), gebruik dan de **officiële Discourse theme component** (zoals Asana).

## Optie 1: discourse-top-contributors-sidebar (aanbevolen)

1. Ga naar **Admin → Customize → Themes**
2. Klik op **Install theme/component** (of **Components**)
3. Voer in: `discourse-top-contributors-sidebar`
4. Of installeer via de URL: `https://github.com/discourse/discourse-top-contributors-sidebar`
5. Voeg de component toe aan je Stripinfo theme
6. Optioneel: Verberg de eigen sectie in `common/common.scss`:
   ```scss
   .si-top-contributors { display: none !important; }
   ```

## Optie 2: Inline script (huidige implementatie)

Controleer:
- **Admin → Settings** → zoek "user directory" → `enable_user_directory` moet **aan** staan
- Test de API in de browserconsole: `fetch('/directory_items.json?period=monthly&order=post_count&limit=5').then(r=>r.json()).then(console.log)`
- Hard refresh (Ctrl+Shift+R) of incognito
