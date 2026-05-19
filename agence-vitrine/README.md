# Studio Pixel — Vitrine d'agence digitale

Landing page complète pour présenter une agence digitale au Maroc : sites web, Meta/Google Ads, vidéo, stratégie marketing, menu digital, logiciels sur mesure.

## Personnaliser avant déploiement

Ouvrez `index.html` et remplacez (Ctrl+H dans VSCode/Notepad++) :

| Chercher | Remplacer par |
|---|---|
| `Studio Pixel` | Nom de votre agence |
| `06 49 23 94 90` (et `+212649239490`) | Votre numéro |
| `RESTAURANT MAÂRIF` (etc.) | Vos vrais clients ou laissez vides |

Pour le logo, modifiez `<span class="brand-logo">▮▮</span>` — vous pouvez mettre une vraie image `<img src="logo.svg" />` à la place.

## Voir en local

Double-clic sur `index.html`, ou :
```bash
python -m http.server 3000
# Puis http://localhost:3000
```

## Déployer sur Vercel

### Méthode rapide (drag & drop)
1. Allez sur https://vercel.com/new
2. Glissez le dossier `agence-vitrine` dans le navigateur
3. Cliquez **Deploy** — en ligne en 30 secondes

### Méthode CLI
```bash
npm i -g vercel
cd agence-vitrine
vercel --prod
```

## Personnaliser les couleurs

Dans `style.css`, en haut :
```css
--accent: #00d9ff;    /* cyan principal */
--accent-2: #ff3d8a;  /* rose accent */
--primary: #0066ff;   /* bleu CTA */
```

## Ajouter de vrais visuels

Les "case-visual" actuels sont des dégradés CSS. Pour vrais screenshots :
```html
<div class="case-visual">
    <img src="images/projet1.jpg" alt="..." />
    <span class="case-tag">SaaS B2B</span>
</div>
```
Ajouter dans CSS :
```css
.case-visual img { width: 100%; height: 100%; object-fit: cover; }
```
