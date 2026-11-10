# Plateforme d'annonces

Application web de gestion d'annonces avec authentification et espace d'administration, construite avec Next.js, Prisma et PostgreSQL.

## Fonctionnalités

- Inscription et connexion avec NextAuth (identifiants et comptes liés)
- Espace d'administration protégé par middleware
- Création, modification et suppression d'annonces (titre, description, image) depuis des fenêtres modales
- Fenêtre de détail d'une annonce
- Gestion des utilisateurs via l'API
- Interface construite avec des composants shadcn/ui et Tailwind CSS

## Technologies

- Next.js 15 (App Router) et React 19
- TypeScript
- NextAuth pour l'authentification
- Prisma et PostgreSQL
- Tailwind CSS et shadcn/ui
- bcrypt pour le hachage des mots de passe

## Structure

```
src/
  app/
    api/ads/       routes et service des annonces
    api/users/     routes et service des utilisateurs
    api/auth/      NextAuth
    [local]/(admin)/ads/   page d'administration des annonces
  components/      composants communs et composants d'interface
  middleware.ts    protection des pages d'administration
prisma/
  schema.prisma    modèles Users, Accounts, Sessions, Ads
  migrations/      historique des migrations
```

## Installation

Prérequis : Node.js 18 ou plus récent et une base PostgreSQL.

```bash
git clone https://github.com/imene-be/classified-ads-platform.git
cd classified-ads-platform
npm install
```

Créez un fichier `.env` à la racine (ce fichier n'est pas versionné) :

```env
DATABASE_URL="postgresql://utilisateur:motdepasse@hote:5432/base"
DIRECT_URL="postgresql://utilisateur:motdepasse@hote:5432/base"
NEXTAUTH_SECRET="une_longue_chaine_aleatoire"
NEXTAUTH_URL="http://localhost:3000"
```

Puis préparez la base et lancez l'application :

```bash
npx prisma generate
npx prisma migrate deploy
npm run dev
```

L'application est disponible sur [http://localhost:3000](http://localhost:3000).

---

Projet réalisé à deux par Nassim Bentifraouine et [Imène Bentifraouine](https://imenebe.fr).
