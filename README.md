# BusTrackDakar

## Notre équipe

| Prénom | Nom | Rôle | GitHub Username | E-mail GitHub |
|---------|---------|---------|---------|---------|
| Khadim | NIASS | PM / Prompt Engineer / Dev UI / Impact | @khadimniass | niassssn@gmail.com |
| Alousseynou dit Makha | DIAW | PM / Prompt Engineer / Dev UI / Impact | @khadimniass |  |
| Mouhamadou Moustapha | ka| PM / Prompt Engineer / Dev UI / Impact | @moustphaka | votre-email@github.com |
| Kombo | Gauthier | PM / Prompt Engineer / Dev UI / Impact | @maliksarr239-beep | gauthierkombo@gmail.com |
## Notre défi

**Secteur :** Supply chain maraîchère (Zone des Niayes)

### Problématique

Comment pourrions-nous aider les maraîchers des Niayes à connaître les prix des marchés de Dakar par SMS afin de réduire l'asymétrie d'information et limiter les marges excessives des intermédiaires ?

## Livrables S1

- [x] Fiche équipe soumise
- [x] Énoncé HMN validé
- [ ] Carte d'empathie (prochaine étape)
--------------------------------------------------
### prompt 1:
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
--------------------------------------------------
### prompt 2:
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
--------------------------------------------------
### prompt 3:
**[PROMPT GÉNÉRATEUR DE HMW — BusTrack Dakar]**

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
--------------------------------------------------
### prompt 4:
**[PROMPT CARTE D'EMPATHIE — BusTrack Dakar]**

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
