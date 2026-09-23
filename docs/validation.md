# Rapport de validation

| Vérification | Requête | Résultat attendu |
| --- | --- | --- |
| Santé du service | `GET https://cp8-lanterne-correction-zeta.vercel.app/api/health` | HTTP 200 et JSON avec `status: ok` |
| Liste | `GET https://cp8-lanterne-correction-zeta.vercel.app/api/curiosities` | HTTP 200 et tableau `data` |
| Recherche | `GET https://cp8-lanterne-correction-zeta.vercel.app/api/curiosities?q=mémoire&limit=1` | HTTP 200, résultat filtré, `meta.count` cohérent |
| Détail | `GET https://cp8-lanterne-correction-zeta.vercel.app/api/curiosities/passage-bleu` | HTTP 200 et objet `data` |
| Ressource absent | `GET https://cp8-lanterne-correction-zeta.vercel.app/api/curiosities/inconnu` | HTTP 404 et réponse JSON |
| Route absente | `GET https://cp8-lanterne-correction-zeta.vercel.app/api/inconnue` | HTTP 404 et réponse JSON |

# Contrôle local complémentaire

```text
pnpm run check
pnpm test
```

# Preuves acceptables

- Captures d'écran de l'onglet Vercel montrant le déploiement et son statut
- Sorties de commandes ou export HTTP anonymisé
- Captures des réponses JSON
- date, URL et version de l'API testé

Les tokens, variables secrètes et données personnelles ne doivent jamais apparaitre dans les preuves.