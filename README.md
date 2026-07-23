# Kali Cognitif — Landing page

Landing page one-page pour Kali Cognitif, activité de coaching en arts martiaux (Kali + boxe
anglaise) en entreprise. Construite avec [Astro](https://astro.build) en mode statique et
[Tailwind CSS v4](https://tailwindcss.com).

## Cloudflare

kali-cognitif.fr
nameservers:
- johnathan.ns.cloudflare.com
- marjory.ns.cloudflare.com


## CRM — Prospection Kali Cognitif


### Sport en entreprise

- Angers - cd49.ffse@gmail.com
  - [x] contact initial
  - [ ] envoi plaquette

- Tours - contact@lcse-sportentreprise.fr
  - [x] contact initial
  - [x] envoi plaquette

### Maisons de quartier

Annuaire SENACS (Système d'Échanges National des Centres Sociaux) pour avoir liste maisons de quartier - filtrable par département : senacs.fr, département 49.

- Saumur
  - Maison des Associations et de Quartier Jean Rostand
    - 330 rue Emmanuel Clairefond, 49400 Saumur
    - 📧 e.launay@ville-saumur.fr — 02 41 83 12 80
    - [x] contact initial
    - [x] envoi plaquette

- Angers
  - Maison de Quartier Angers Centre — 12 rue Thiers, 49100 Angers
    -
    - [ ] contact initial
    - [ ] envoi plaquette

  - L'Archipel Espace d'Animation — 13 bis bd Georges Clemenceau, 49000 Angers
    - direction@larchipelasso.fr - accueil@larchipelasso.fr - https://larchipelasso.centres-sociaux.fr/ - 02 41 24 89 10
    - [x] contact initial
    - [x] envoi plaquette

  - Maison Pour Tous Monplaisir — 3 rue de l'Écriture, 49000 Angers
    - contact@mpt-monplaisir.fr - http://mpt-monplaisir.fr - 02 41 43 84 09
    - [x] contact initial
    - [x] envoi plaquette

  - Les trois mats
    - troismats.accueil@gmail.com - troismats.direction@gmail.com - +33 (0)2 41 66 02 02 - http://www.letroismats.fr
    - [x] contact initial
    - [x] envoi plaquette

  - CENTRE SOCIAL JEAN VILAR ANGERS
    - centre.jean-vilar@ville.angers.fr - http://www.angers.fr/vivre-a-angers/quartiers/roseraie/centre-jean-vilar/index.html
    - [x] contact initial
    - [x] envoi plaquette


### Agences Évènementielles / Séminaires
- Hatch Event
  - Angers (siège) + Grand Ouest : Saumur, Cholet, Tours, Nantes
  - 06 59 12 94 12 — formulaire sur hatch-event.com/contact
  - [x] contact initial
  - [x] envoi plaquette
- Agence Sensorielle
  - Saumur, entre Angers et Tours
  - contact@agencesensorielle.com — 02 41 52 65 44
  - [x] contact initial
  - [x] envoi plaquette
- Loire Secrets
  - Angers, Saumur, Tours, Nantes, Blois
  - contact@loiresecrets.com — 02 41 91 94 76
  - [x] contact initial
  - [x] envoi plaquette
- INNOV'events
  - Angers, mentionne explicitement les caves troglodytiques du Saumurois
  - eva@innov-events.fr - 09 67 71 73 13 (contact direct : Eva France)
  - [x] contact initial
  - [x] envoi plaquette

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
