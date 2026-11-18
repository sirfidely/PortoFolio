# Portfolio et journal de bord — Fidel Mondésir N'zoué

Site Jekyll : portfolio, fiches projets, blog (journal de bord) et backoffice sur `/admin`.

## Structure

| Dossier / fichier | Contenu |
|---|---|
| `index.html` | Page d'accueil du portfolio |
| `_projets/` | Une fiche par projet ou activité (une page `/projets/nom/` chacune) |
| `_posts/` | Les articles du blog, chacun rattaché à un projet |
| `_data/geniuspay.yml` | Les chiffres GeniusPay affichés sur l'accueil |
| `_data/contact.yml` | E-mail, téléphone, LinkedIn, photo |
| `admin/` | Le backoffice (Sveltia CMS) |

## Utiliser le backoffice

1. Ouvrir `https://geniuslabs.tech/admin/`.
2. Choisir **Sign In with Token** et coller un jeton GitHub (voir plus bas).
3. Écrire un article, choisir le projet concerné, ajouter les sources, puis **Save**.
   Chaque enregistrement crée un commit sur `main` ; le site se met à jour en 1 à 2 minutes.

### Créer le jeton GitHub (une seule fois)

GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token.
Accès au seul dépôt `sirfidely/portofolio`, permission **Contents : Read and write**. Garder ce jeton privé.

## Mettre en ligne sur geniuslabs.tech avec GitHub Pages

1. Dépôt → **Settings → Pages** → *Deploy from a branch*, branche `main`, dossier `/ (root)`.
2. Dans le même écran, **Custom domain** : `geniuslabs.tech`, puis cocher *Enforce HTTPS*.
3. Chez le registrar du domaine, créer les enregistrements DNS :
   - `A` pour `@` vers `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` pour `www` vers `sirfidely.github.io`

Pour un autre hébergeur : lancer `bundle install` puis `bundle exec jekyll build`, et publier le dossier `_site/`.

## Voir le site en local

```bash
bundle install
bundle exec jekyll serve
```
