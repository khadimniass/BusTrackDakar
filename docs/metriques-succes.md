## Métriques de Succès — OnTime DAKAR

### MVP

Un service accessible par SMS ou navigateur mobile léger qui permet à un usager des bus DDD de connaître l'heure estimée d'arrivée de son bus à son arrêt, sans application à installer, sur la ligne pilote Guédiawaye → Plateau. L'estimation est produite à partir d'un signal de départ terminus et des horaires historiques, avec un indicateur de fiabilité affiché.

---

### ⭐ Métrique Nord

**Indicateur :** Taux de retour — proportion d'usagers ayant utilisé le service au moins deux fois sur deux jours différents dans la même semaine, sans relance de l'équipe.

**Valeur cible à 30 jours :** 60 % des usagers recrutés sur la ligne pilote reviennent spontanément.

**Comment mesurer :** Journal papier tenu par le "sentinelle" recruté à l'arrêt — chaque usager qui demande une ETA coche son pseudonyme dans un tableau à deux colonnes (Jour 1 / Jour 2+). Comptage hebdomadaire manuel par Kombo GAUTHIER.

---

### 📈 Métriques de Progression

#### Métrique P1

**Indicateur :** Précision ETA — nombre de fois où le bus arrive dans la fenêtre annoncée ±5 minutes.

**Valeur cible à 30 jours :** 6 trajets corrects sur 10 observés en heure de pointe (7h-9h).

**Comment mesurer :** Fiche terrain A5 — l'observateur note l'heure ETA affichée et l'heure réelle d'arrivée du bus au chronomètre. 10 observations par semaine suffisent. Pas de capteur, pas d'app.

---

#### Métrique P2

**Indicateur :** Taux de signal conducteur — nombre de départs terminus signalés par SMS ou USSD sur le nombre total de départs observés sur la ligne pilote.

**Valeur cible à 30 jours :** 7 signaux sur 10 départs (70 %) sur la semaine 3 et au-delà.

**Comment mesurer :** Comptage des SMS/USSD reçus côté serveur vs nombre de départs réels notés par l'observateur au terminus. Tableau hebdomadaire partagé sur le groupe WhatsApp équipe.

---

#### Métrique P3

**Indicateur :** Adoption organique — nombre d'usagers qui utilisent le service sans avoir été recrutés directement par l'équipe (bouche-à-oreille).

**Valeur cible à 30 jours :** 10 usagers non recrutés identifiés sur la ligne pilote.

**Comment mesurer :** Question systématique posée à chaque nouvel usager par le sentinelle : *"Comment tu as connu le service ?"* — réponse notée dans le journal papier. Toute réponse autre que "l'équipe m'a contacté" compte comme adoption organique.

---

### 🚨 Métriques d'Alerte

#### Alerte A1

**Signal :** ETA systématiquement fausse — précision tombe sous le seuil critique.

**Seuil :** Moins de 4 arrivées correctes sur 10 deux semaines consécutives (précision < 40 %).

**Action corrective :** Suspension immédiate de l'affichage d'une heure précise — remplacement par un intervalle large ("dans 10 à 20 min") jusqu'à recalibration du modèle d'estimation ; réunion équipe sous 48h pour identifier la cause (signal conducteur manquant, trafic atypique, données historiques insuffisantes).

---

#### Alerte A2

**Signal :** Abandon du signal conducteur — le taux de départs signalés chute brutalement.

**Seuil :** Moins de 3 signaux sur 10 départs sur une semaine (< 30 %).

**Action corrective :** Entretien terrain immédiat avec le conducteur ou agent concerné pour comprendre le blocage (charge de travail, oubli, problème technique) ; activation du plan B — crowdsourcing usagers comme source de signal de départ de secours, avec recrutement de 3 sentinelles supplémentaires à l'arrêt.

---

### Tableau de Bord S6

À la démo S6, nous présenterons ces 3 chiffres :

1. **Taux de retour spontané** — valeur réelle vs cible 60 % *(Métrique Nord — le MVP crée-t-il de la valeur répétée ?)*
2. **Précision ETA** — nombre de trajets corrects à ±5 min vs cible 6/10 *(P1 — la promesse technique est-elle tenue ?)*
3. **Alerte A2** — déclenchée ou non *(la source de données tient-elle sans intervention de l'équipe ?)*
