# Procédure de déploiement

## 1. Prérequis

- Node.js 24 LTS
- pnpm 11
- Un repository Github
- Un compte Vercel
- Le dossier du projet configuré comme répertoire racine du projet Vercel

La version Node.js doit être cohérente entre le développement local, le dépôt et Vercel.
Le fichier `.nvmrc` fixe Node.js 24 pour éviter un environnement implicite.

## 2. Installation locale

```text
pnpm install ci
pnpm run check
pnpm test
```

Résultats attendus : 
```text
node --check api/index.js && node --check tests/api.test.js
API tests passed
```

## 3. Déploiement Vercel

Depuis la racine du projet : 

``` 
vercel link
> Create a new project
> Name : Nommez le projet ou appuyez sur entrer
> Connect this Git repository to automatically deploy changes on every push : N
> Code directory : Laisser par défaut
> Customize settings : N
```
ensuite déployer avec 
`vercel`

## Mise à jour

Pour publier une nouvelle version :

1. Passer sur la branche develop : `git switch develop`
2. Mettre à jour le projet
3. Mettre à jour les tests si le comportement change
4. Lancer `pnpm run check` et `pnpm test`
5. Créer un commit explicite
6. Déployer la preview : ``