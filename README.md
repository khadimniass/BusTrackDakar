# 🚌 BusTrackDakar

> **GET 409 · Atelier IA · Master · Swiss UMEF University — Campus de Dakar · 2025-2026**

---

## Le problème

Les usagers des bus DDD (Dakar Dem Dikk) attendent en moyenne **25 à 40 minutes** sans aucune information sur la position ou l'heure d'arrivée de leur bus. Faute de visibilité, ils subissent leur trajet — et perdent tout pouvoir de décision.

## Notre réponse

> **Comment pourrions-nous** permettre aux usagers des bus DDD de Dakar de connaître en temps réel la position et l'heure d'arrivée de leur bus, afin de réduire les attentes imprévisibles et reprendre le contrôle de leurs trajets ?

---

## L'équipe

| Prénom | Nom | Rôle | GitHub |
|---|---|---|---|
| Khadim | NIASS | Chef de Produit (PM) | [@khadimniass](https://github.com/khadimniass) |
| Alousseynou dit Makha | DIAW | Master Prompt Engineer | [@alousseynoumakha](https://github.com/alousseynoumakha) |
| Mouhamadou Moustapha | KA | Dev UI (No-Code) | [@moustphaka](https://github.com/moustphaka) |
| Kombo | GAUTHIER | Responsable Impact | [@gauthierkombo](https://github.com/gauthierkombo) |

---

## Documentation

| Document | Description |
|---|---|
| [📋 Fiche équipe](docs/fiche-equipe.md) | Identité, membres, rôles, infrastructure S1 |
| [🗺️ Carte d'empathie](docs/carte-empathie.md) | Persona Moussa — pains, gains, insights |
| [🎩 6 Chapeaux de Bono](docs/chapeaux-bono.md) | Analyse S2 — faits, risques, idées, synthèse |
| [🚫 Contraintes MVP](docs/contraintes-mvp.md) | Critères non négociables — ce qu'on construit et ce qu'on élimine |
| [🔬 Hypothèses de validation](docs/hypotheses-validation.md) | Hypothèses CRITIQUES / IMPORTANTES / SECONDAIRES — plan S3 |
| [📊 Métriques de succès](docs/metriques-succes.md) | Métrique Nord, progression, alertes — tableau de bord S6 |
| [🎯 Value Proposition Canvas](docs/vpc.md) | Jobs, pains, gains — FIT Check complet |
| [🔗 Traçabilité VPC](docs/vpc-connections.md) | Connexions 6 Chapeaux → VPC — cohérence validée |
| [📦 Backlog S3](docs/backlog-s3.md) | User stories MUST / SHOULD / COULD — sprint S3 |
| [❓ HMW Définitif](docs/hmw-definitif.md) | HMW validé S2 — version retenue pour le prototypage |
---

## Prompts S1

<details>
<summary>Prompt 1 — Découverte du problème</summary>

```
Tu es un expert en mobilité urbaine et transport en commun à Dakar, Sénégal.

Identifie les 3 principaux problèmes que rencontrent les usagers
des bus DDD/Dakar Dem Dikk dans le contexte urbain dakarois
(connectivité limitée, densité du trafic, informalité du réseau).

Pour chaque problème :
- La cause principale
- L'impact sur la vie quotidienne de l'usager dakarois
- Une piste de solution technologique accessible (offline-first,
  compatible feature phones ou bas débit)
```

</details>

<details>
<summary>Prompt 2 — Guide d'interview</summary>

```
Tu es un UX Researcher spécialisé dans les usages numériques en Afrique de l'Ouest.

Je dois interviewer [usager quotidien des bus urbains à Dakar
(DDD, cars rapides) — actif, smartphone basique ou entrée de gamme,
connectivité 2G/3G intermittente] face au problème :
[Il est impossible de savoir quand le prochain bus arrive
ni où il se trouve, ce qui cause des attentes imprévisibles
et des retards subis.]

Génère un guide d'interview avec :
1. 3 questions d'ouverture (brise-glace)
2. 5 questions d'exploration en profondeur
   (avec 'Pourquoi ?' et 'Racontez-moi...')
3. 2 questions sur les aspirations attendues

Format : questions numérotées, courtes, sans jargon.
```

</details>

<details>
<summary>Prompt 3 — Générateur HMW</summary>

```
Tu es un facilitateur en Design Thinking.

Voici nos observations clés de l'interview :
Observation 1 : [Les usagers attendent en moyenne 25-40 min
                 sans aucune information sur l'arrivée du bus]
Observation 2 : [Ils appellent des proches déjà dans le bus
                 pour estimer l'heure d'arrivée]
Observation 3 : [Beaucoup abandonnent le bus pour un jakarta
                 ou taxi après une longue attente incertaine]

Frustration principale : [L'usager dakarois subit son trajet
faute de visibilité sur la position et l'heure d'arrivée
de son bus, ce qui le prive de tout pouvoir de décision.]

Génère 5 énoncés 'Comment pourrions-nous...' (HMW)
qui reformulent cette frustration en opportunité.

Critères : ni trop vague, ni trop précis,
ne propose pas encore de solution.
```

</details>

<details>
<summary>Prompt 4 — Carte d'empathie</summary>

```
# ROLE
Tu es un UX Researcher expert pour des projets
d'innovation sociale en Afrique.

## PERSONA
- Prénom, âge, profession : [Moussa, 28 ans, employé de bureau à Plateau]
- Localisation : [Guédiawaye, Dakar, Sénégal]
- Problème : [Il ne sait jamais quand son bus DDD arrive
               et rate souvent des réunions importantes]
- Équipement digital : [Smartphone Android entrée de gamme,
                        connexion 3G intermittente]

## OBSERVATIONS DE NOS INTERVIEWS
- Ce qu'il/elle a dit : ["Je préfère partir 1h plus tôt
                          que de rater mon bus sans savoir"]
- Ce qu'il/elle a fait : [Appelle un collègue déjà dans le bus
                           pour estimer l'heure d'arrivée]
- Émotion principale : [Frustration mêlée de résignation]

## FORMAT STRICT
### 1. PENSE ET RESSENT  - [Insight 1]  - [Insight 2]
### 2. VOIT              - [Insight 1]  - [Insight 2]
### 3. ENTEND            - [Insight 1]  - [Insight 2]
### 4. DIT ET FAIT       - [Comportement]  - [Citation]
### 5. FRUSTRATIONS (Pains)  - [Douleur principale]
### 6. ASPIRATIONS (Gains)   - [Résultat désiré]
```

</details>

---

*Enseignant responsable : M. Malick Faye Diagne — GET 409 · Swiss UMEF University Dakar*
