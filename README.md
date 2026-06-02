# 🚌 BusTrackDakar
> GET 409 · Atelier IA · Master · Swiss UMEF University — Campus de Dakar · 2025-2026

---

## 👥 Notre équipe

| Prénom | Nom | Rôle | GitHub Username | E-mail GitHub |
|---|---|---|---|---|
| Khadim | NIASS | Chef de Produit (PM) | @khadimniass | niassssn@gmail.com |
| Alousseynou dit Makha | DIAW | Master Prompt Engineer | @alousseynoumakha | alousseynoumakha@gmail.com |
| Mouhamadou Moustapha | KA | Dev UI | @moustphaka | moustphakha@gmail.com |
| Kombo | GAUTHIER | Responsable Impact | @gauthierkombo | gauthierkombo@gmail.com |

---

## 🎯 Notre défi

**Secteur :** Mobilité urbaine — Transport en commun (Dakar)

### Problématique

> Comment pourrions-nous permettre aux usagers des bus DDD de Dakar de connaître en temps réel la position et l'heure d'arrivée de leur bus, afin de réduire les attentes imprévisibles et reprendre le contrôle de leurs trajets ?

---

## ✅ Livrables S1

- [x] Fiche équipe soumise sur e-Academy
- [x] Énoncé HMW validé
- [ ] Carte d'empathie — à déposer sur e-Academy avant **20h45**
- [ ] Dépôt GitHub `GET409-BusTrackDakar` — README.md + tous les membres en collaborateurs
- [ ] Compte Dify activé — espace de travail équipe créé sur [dify.ai](https://dify.ai)
- [ ] Commit GitHub avant **minuit**

---

## 🤖 Prompts S1

### Prompt 1 — Découverte du problème

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

---

### Prompt 2 — Guide d'interview

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

---

### Prompt 3 — Générateur HMW

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

---

### Prompt 4 — Carte d'empathie

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

---
*M. Malick Faye Diagne — Enseignant responsable · GET 409 · Swiss UMEF University Dakar*
