# Site vitrine Nupsio

Site statique (une seule page). Aucun build, aucune dépendance : il suffit de servir les fichiers.

```
index.html          la page
assets/             logo, favicon et captures d'écran
CNAME               domaine personnalisé (nupsio.com) pour GitHub Pages
.nojekyll           désactive le traitement Jekyll de GitHub Pages
robots.txt          indexation
sitemap.xml         plan du site
```

## Mise en ligne sur GitHub Pages

1. Sur github.com, créer un dépôt public `nupsio-site`.
2. Uploader le **contenu** de ce dossier à la racine du dépôt (index.html doit être à la racine, pas dans un sous-dossier).
3. Dépôt → **Settings** → **Pages** → Source : `Deploy from a branch`, Branch : `main`, dossier `/ (root)` → Save.
4. Attendre 1 à 2 minutes : le site est en ligne sur `https://<votre-compte>.github.io/nupsio-site/`.

## Brancher le domaine nupsio.com

Chez votre registrar (celui où nupsio.com est acheté), créer ces enregistrements DNS :

| Type  | Nom / Hôte | Valeur                  |
|-------|------------|-------------------------|
| A     | @          | 185.199.108.153         |
| A     | @          | 185.199.109.153         |
| A     | @          | 185.199.110.153         |
| A     | @          | 185.199.111.153         |
| CNAME | www        | `<votre-compte>.github.io` |

Attention : ne touchez pas à l'enregistrement existant de `app` (le sous-domaine app.nupsio.com de l'application).

Puis dans GitHub : **Settings** → **Pages** → **Custom domain** → saisir `nupsio.com` → Save, et cocher **Enforce HTTPS** dès que la case devient disponible (quelques minutes à quelques heures après la propagation DNS).

Le fichier `CNAME` présent dans ce dossier contient déjà `nupsio.com` : GitHub le lira automatiquement.

## Mise à jour du site

Remplacez `index.html` (et les images d'`assets/` si besoin) dans le dépôt : GitHub Pages redéploie tout seul en une minute.
