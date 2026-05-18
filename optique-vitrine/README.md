# Optique Manager — Site vitrine

Landing page statique en français pour présenter **Optique Manager**, le logiciel de gestion pour opticiens marocains.

## Contenu

```
optique-vitrine/
├── index.html      ← La page (HTML sémantique, 1 seule page)
├── style.css       ← Le style (modern, responsive, dark footer)
├── vercel.json     ← Config Vercel (cache + headers de sécurité)
└── README.md       ← Ce fichier
```

**Aucune dépendance JS, aucun build step.** C'est du HTML/CSS pur, ça se charge en 200 ms.

## Voir en local

Double-cliquez simplement sur `index.html` — le navigateur l'ouvre. Ou bien :

```bash
# Avec Python (souvent déjà installé) :
cd optique-vitrine
python -m http.server 3000

# Avec Node :
npx serve .
```

Puis ouvrez http://localhost:3000

## Déployer sur Vercel

### Méthode 1 — Vercel CLI (la plus rapide)

```bash
npm i -g vercel        # installer Vercel CLI (une seule fois)
cd optique-vitrine
vercel                 # déploiement de prévisualisation
vercel --prod          # déploiement en production
```

Vercel détecte automatiquement que c'est un site statique. La première fois, il vous demande :
- À quelle organisation lier le projet
- Quel nom de projet
- Quel dossier déployer (gardez `./`)

### Méthode 2 — Drag & drop dans le dashboard Vercel

1. Connectez-vous à https://vercel.com
2. Cliquez sur **« Add New Project »** → **« Browse all templates »** → en bas **« Import from local »**
3. Glissez le dossier `optique-vitrine` dans la zone
4. Cliquez **Deploy**

C'est en ligne en 30 secondes.

### Méthode 3 — Via GitHub (recommandée pour le long terme)

```bash
cd optique-vitrine
git init
git add -A
git commit -m "Initial commit"
git branch -M main

# Créer un repo GitHub puis :
git remote add origin https://github.com/VOTRE-USERNAME/optique-vitrine.git
git push -u origin main
```

Puis sur https://vercel.com → **Add New Project** → connectez votre GitHub → choisissez le repo → **Deploy**.

À chaque `git push`, Vercel redéploie automatiquement.

## Personnaliser le contenu

### Modifier le numéro de téléphone et l'email
Ouvrez `index.html`, cherchez la section CTA (`id="contact"`) et remplacez :
- `contact@optique-manager.ma` par votre vraie adresse email
- `+212600000000` par votre vrai numéro de téléphone

### Ajouter de vraies captures d'écran
La maquette actuelle dans le hero est faite en CSS. Pour utiliser de vraies captures :
1. Ajoutez vos images dans `optique-vitrine/images/`
2. Remplacez le bloc `<div class="hero-mockup">` par `<img src="images/dashboard.png" alt="Tableau de bord Optique Manager" />`

### Changer la couleur principale
Dans `style.css`, modifiez les variables CSS au début du fichier :
```css
:root {
    --primary: #10b981;        /* couleur principale */
    --primary-dark: #059669;   /* version foncée */
    --primary-light: #d1fae5;  /* version claire */
}
```

## Domaine personnalisé

Une fois le site déployé sur Vercel, dans le dashboard du projet :
**Settings → Domains → Add** → entrez votre domaine (ex. `optique-manager.ma`) et suivez les instructions DNS.

Vercel fournit HTTPS automatiquement et gratuitement.

## SEO

Les balises meta de base sont déjà configurées :
- `<title>` — titre de la page
- `meta description` — résumé pour Google
- `meta keywords` — mots-clés (CNSS, CNOPS, opticien Maroc, etc.)

Pour aller plus loin, vous pouvez ajouter :
- Une sitemap.xml
- Un robots.txt
- Des données structurées Schema.org (`SoftwareApplication`)
- Un favicon haute résolution (`favicon-512.png`)
