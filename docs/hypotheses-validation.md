## Hypothèses de Validation — OnTime DAKAR

### HMW Définitif

"Comment pourrions-nous permettre aux usagers des bus DDD de Dakar d'estimer fiablement l'heure d'arrivée de leur bus — même sans connexion stable — afin qu'ils puissent décider en toute autonomie d'attendre ou de prendre une alternative ?"

---

### Hypothèses CRITIQUES

*(Si fausse → le MVP ne fonctionne pas)*

#### Hypothèse C1

**Affirmation :** Nous croyons qu'il existe une source de données de position alternative à un GPS embarqué DDD — conducteur, usager fréquent, ou agent de terminus — prête à produire un signal de départ/arrivée sans friction et sans rémunération.

**Indicateur :** Nous le saurons si au moins 2 conducteurs ou agents de terminus sur la ligne pilote (Guédiawaye → Plateau) acceptent d'envoyer un SMS ou de taper un USSD au départ du terminus lors d'un test de 3 jours consécutifs.

**Méthode :** Test terrain — approche directe au terminus de Guédiawaye, observation du comportement réel (pas déclaratif).

**Qui valide :** Kombo GAUTHIER (Responsable Impact) + un conducteur volontaire recruté sur place.

**Délai S3 :** Semaine 1 — bloquant pour toute la suite.

---

#### Hypothèse C2

**Affirmation :** Nous croyons que Moussa et les usagers similaires sont capables d'obtenir une ETA via SMS ou interface web légère sans assistance, depuis un smartphone Android entrée de gamme avec connexion 3G intermittente.

**Indicateur :** Nous le saurons si 4 usagers sur 5 recrutés au terminus de Guédiawaye obtiennent une réponse ETA en moins de 3 tentatives, sans aide de l'équipe, lors d'un test de 10 minutes.

**Méthode :** Test utilisateur terrain — prototype papier ou maquette Figma sur le téléphone du testeur, observation silencieuse.

**Qui valide :** Mouhamadou Moustapha KA (Dev UI) — observation et prise de notes comportementales.

**Délai S3 :** Semaine 1-2 — aucun développement avant ce test.

---

#### Hypothèse C3

**Affirmation :** Nous croyons qu'une estimation d'heure d'arrivée basée sur les horaires historiques et un signal de départ terminus est suffisamment fiable pour que Moussa fasse confiance à l'information et modifie son comportement (partir plus tard, ne pas appeler un ami).

**Indicateur :** Nous le saurons si l'ETA estimée est correcte à ±5 minutes dans au moins 6 trajets sur 10 observés sur la ligne pilote en heure de pointe.

**Méthode :** Observation terrain — chronomètre réel vs ETA calculée sur 10 passages consécutifs de la ligne pilote, une semaine de données.

**Qui valide :** Alousseynou DIAW (Prompt Engineer / data) + Khadim NIASS (PM, décision go/no-go).

**Délai S3 :** Semaine 2 — conditionne la promesse de fiabilité du produit.

---

### Hypothèses IMPORTANTES

*(Si fausse → expérience dégradée mais MVP utilisable)*

#### Hypothèse I1

**Affirmation :** Nous croyons que l'indicateur de fiabilité affiché avec l'ETA ("estimé", "confirmé", "données anciennes") réduit la frustration en cas d'inexactitude plutôt que de l'amplifier.

**Indicateur :** Nous le saurons si, lors du test utilisateur, aucun des 5 testeurs n'exprime de confusion ou de méfiance accrue face à l'indicateur de fiabilité — mesuré par observation et question ouverte post-test : "Qu'est-ce que ce message vous dit ?"

**Méthode :** Test utilisateur avec debriefing verbal de 5 minutes post-tâche.

**Qui valide :** Mouhamadou Moustapha KA — observation + verbatims notés.

**Délai S3 :** Semaine 2, en même temps que C2.

---

#### Hypothèse I2

**Affirmation :** Nous croyons que la connexion 3G à Guédiawaye est suffisante pour charger une réponse ETA en moins de 3 secondes depuis le serveur, aux heures de pointe (7h-9h).

**Indicateur :** Nous le saurons si le temps de réponse mesuré depuis un smartphone Android entrée de gamme au terminus de Guédiawaye est inférieur à 3 secondes dans au moins 8 cas sur 10 entre 7h et 9h sur 3 jours de test.

**Méthode :** Test technique terrain — requête chronométrée depuis le réseau mobile réel, aucune simulation WiFi.

**Qui valide :** Mouhamadou Moustapha KA (Dev UI).

**Délai S3 :** Semaine 2 — parallèle au test utilisateur C2.

---

#### Hypothèse I3

**Affirmation :** Nous croyons que Moussa est prêt à signaler le passage d'un bus (un tap ou un SMS) en échange d'une ETA plus fiable — et que ce comportement tient dans le temps sans rémunération.

**Indicateur :** Nous le saurons si au moins 3 usagers recrutés au terminus envoient un signal de confirmation volontaire lors de 2 trajets consécutifs sur une période de 5 jours, sans relance de l'équipe.

**Méthode :** Test comportemental terrain — recrutement de 5 "sentinelles" volontaires, suivi passif des signaux reçus.

**Qui valide :** Kombo GAUTHIER (Responsable Impact) — suivi et analyse de rétention.

**Délai S3 :** Semaine 2-3.

---

### Hypothèses SECONDAIRES

*(À valider après le MVP)*

#### Hypothèse S1

**Affirmation :** Nous croyons qu'un passage en wolof de l'interface SMS augmente le taux d'adoption chez les usagers non francophones.

**Indicateur :** Nous le saurons si le taux de complétion de la tâche ETA est supérieur de 20 % en wolof vs français sur un panel de 10 usagers non-francophones.

**Méthode :** A/B test sur deux groupes de testeurs terrain.

**Qui valide :** Kombo GAUTHIER + recrutement communautaire.

**Délai S3 :** Post-MVP, sprint suivant.

---

#### Hypothèse S2

**Affirmation :** Nous croyons qu'une extension de la solution à une deuxième ligne DDD est possible sans refonte de l'architecture, une fois la ligne pilote validée.

**Indicateur :** Nous le saurons si le temps d'intégration d'une nouvelle ligne est inférieur à 2 jours de travail sans bug critique en production.

**Méthode :** Test d'extensibilité technique en interne.

**Qui valide :** Mouhamadou Moustapha KA.

**Délai S3 :** Semaine 4 ou post-MVP.

---

### Priorité de Validation S3

La première chose à tester en S3 : **aller au terminus de Guédiawaye dès la semaine 1, recruter un conducteur et 5 usagers, et vérifier en conditions réelles si un signal de départ SMS est produisible et si une ETA sans GPS est lisible et crédible** — tout le reste est secondaire jusqu'à ce que C1, C2 et C3 soient tranchées.
