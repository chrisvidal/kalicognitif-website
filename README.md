# Kali Cognitif — Landing page

Landing page one-page pour Kali Cognitif, activité de coaching en arts martiaux (Kali + boxe
anglaise) en entreprise. Construite avec [Astro](https://astro.build) en mode statique et
[Tailwind CSS v4](https://tailwindcss.com).

## Développement local

```bash
npm install
npm run dev
```

Le site est servi sur `http://localhost:4321`.

Autres commandes utiles :

```bash
npm run build    # build de production dans dist/
npm run preview  # prévisualise le build de production en local
```

## Ajouter les vidéos YouTube

Les vidéos de la section « Le Kali Cognitif en vidéo » sont définies dans un seul tableau en
haut de [src/pages/index.astro](src/pages/index.astro) :

```ts
const videos = [
  { id: "VIDEO_ID", titre: "Titre de la vidéo", description: "Description courte" },
];
```

Remplacez les `id` placeholders (marqués `// TODO`) par les vrais identifiants YouTube — aucune
autre modification n'est nécessaire, la mise en page et le lazy-loading (facade `lite-youtube`
maison) s'adaptent automatiquement.

## Déploiement sur GitHub Pages

Le déploiement est automatisé via GitHub Actions ([.github/workflows/deploy.yml](.github/workflows/deploy.yml)) :
à chaque push sur `main`, le site est buildé puis publié sur GitHub Pages.

Pour l'activer sur un nouveau repo GitHub :

1. Poussez ce projet sur GitHub.
2. Dans les **Settings** du repo → **Pages**, sous « Build and deployment », choisissez la
   source **GitHub Actions**.
3. Le prochain push sur `main` déclenchera le déploiement automatiquement.

## Nom de domaine personnalisé

Le fichier [public/CNAME](public/CNAME) contient `kalicognitif.fr` et sera copié tel quel dans
le build. Configurez chez votre registrar les enregistrements DNS pointant vers GitHub Pages
(voir la [documentation GitHub](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site)),
puis renseignez le même domaine dans Settings → Pages → Custom domain.

## À personnaliser

- `public/images/og-image.jpg` : image Open Graph générée à titre de placeholder — à remplacer
  par un vrai visuel de la plaquette si besoin.
- `src/pages/index.astro` : tableau `videos` pour les vraies vidéos YouTube.
