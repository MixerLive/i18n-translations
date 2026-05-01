# Community Translations

This folder contains locale JSON files used by the frontend runtime.

## How locale files work

- File naming: `<locale>.json` (examples: `en.json`, `es.json`, `fr.json`)
- Locale selection order:
  1. URL query string (`?lang=es` or `?locale=es`)
  2. `localStorage.locale`
  3. `locale` cookie
  4. Browser language
  5. Fallback: `en`
- The frontend fetches locale files from `/assets/i18n/<locale>.json`.

## JSON shape

```json
{
  "meta": {
    "locale": "es",
    "name": "Espanol",
    "direction": "ltr"
  },
  "strings": {
    "Home": "Inicio"
  }
}
```

- `strings` keys are the original source text.
- Values are translated text.
- Variables can be used with `{{name}}` syntax.

## Important translation rule

Do not translate user-generated content like stream titles, descriptions, usernames, or channel names.
Only translate static interface text.

## Contribution flow

1. Fork the repo.
2. Add or edit a locale file in this folder.
3. Open a pull request with your locale changes.
4. Explain the reasons for you proposed changes, espcially when you change an already existing translation.
5. Wait for moderator review it.
6. Apply any changes from review.
7. Merged or rejected.

## Missing elements

If you find a missing translation/static text, feel free to add it and it will be ajusted in the backend.
These "placeholder" names may be changed later. expect things to break in the future. 
NOTE: ANYTHING WITH data-i18n-ignore WILL NOT BE TRANSLATED