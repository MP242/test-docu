# i18n

## Site config

docusaurus.config.ts

```
  i18n: {
    defaultLocale: 'en',
    locales: ['en', 'fr'],
    localeConfigs: {
      en: {
        htmlLang: 'en-GB',
      },
      fr: {
        htmlLang: 'fr-FR',
      },
    },
  },
```

## Dropdown language dans la navbar

docusaurus.config.ts

```
export default {
  themeConfig: {
    navbar: {
      items: [
        {
          type: 'localeDropdown',
          position: 'left',
        },
      ],
    },
  },
};
```

## Rajouter la balise <Translate> dans le fichier index.tsx

src/pages/index.tsx

```
<Translate>Hello World</Translate>
```

## Generer les fichiers de traduction

```
npm run docusaurus write-translations
```

## Modifier les fichiers de traduction

i18n/fr/code.json

```
{
  "Hello World": "Hello World en français"
}
```

## Translate la doc ou le blog

Tu dois copier le fichier en question dans le dossier i18n/fr/docs/

```
cp -r docs/** i18n/fr/docusaurus-plugin-content-docs/current
```

# versionning

## Création d'une nouvelle version

```
npm run docusaurus docs:version 1.0.0
```

## Modifier la configuration pour le dropdown

docusaurus.config.ts

```
{
          label: 'Version',
          position: 'left',
          items: [
            { label: 'Latest', to: 'docs/intro' }, // Version actuelle
            { label: '1.0.0', to: 'docs/1.0.0/intro' }, // Ancienne version
          ],
        },
```

## Générer une autre version

```
npm run docusaurus docs:version 1.1.0
```

## Modifier le fichier index de la nouvelle version

versioned_docs/version-1.1.0/intro.md
