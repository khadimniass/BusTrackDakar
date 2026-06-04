Voici le résultat du prompt P-CHAPEAUX, enrichi avec les données réelles sur DDD :

---

# 6 Chapeaux de Bono — OnTime DAKAR

## HMW analysé

Comment pourrions-nous permettre aux usagers des bus DDD de Dakar de connaître en temps réel la position et l'heure d'arrivée de leur bus, afin de réduire les attentes imprévisibles et leur redonner le contrôle de leurs trajets ?

---

## 🤍 Chapeau Blanc — Faits & Données

- DDD opère 24 lignes avec environ 100 bus par jour pour 120 000 passagers — un ratio très faible qui explique structurellement les intervalles longs entre passages
- Une étude de 2022 révèle que DDD ne couvre que 6 % de la demande de transport à Dakar, ce qui signifie que Moussa n'a souvent aucune alternative crédible au bus DDD sur son trajet Guédiawaye–Plateau
- Un système SMS de tracking (DDDT) a déjà été testé sur DDD mais abandonné en raison du volume et du coût des SMS — preuve que le besoin existe, mais que la solution doit être plus légère

---

## ❤️ Chapeau Rouge — Émotions & Intuitions

- La résignation de Moussa (*"c'est comme ça ici"*) masque une attente réelle de changement — le premier outil fiable créera un effet "wow" immédiat et une adoption rapide par bouche-à-oreille
- L'acte d'appeler un ami déjà dans le bus est un signal fort d'appartenance communautaire — une solution qui s'appuie sur le collectif (crowdsourcing de position) sera perçue comme naturelle, pas comme une technologie froide
- La peur du retard professionnel est le déclencheur émotionnel principal — Moussa ne cherche pas une appli, il cherche à ne plus avoir honte d'arriver en retard devant son supérieur

---

## 🖤 Chapeau Noir — Risques & Critique

- DDD ne dispose pas de GPS embarqué sur tous ses bus, et le renouvellement de flotte prévu avec Iveco a été retardé à plusieurs reprises — sans donnée de position côté opérateur, toute solution de tracking dépend d'une instrumentation que l'équipe ne contrôle pas
- La connectivité 3G intermittente à Guédiawaye signifie que l'application tombera en panne exactement aux heures de pointe, quand le trafic réseau est le plus saturé — sans mode offline, la solution empire la frustration au lieu de la résoudre
- Les usagers ont une perception favorable du prix et du temps de trajet mais des préoccupations persistantes sur les temps d'attente — si la solution affiche une ETA inexacte, la perte de confiance sera immédiate et difficile à récupérer

---

## 💛 Chapeau Jaune — Optimisme & Valeur

- Le marché est massif et captif : 250 000 usagers quotidiens sur le réseau urbain — même une adoption partielle représente un impact à grande échelle
- Le précédent DDDT prouve que DDD est réceptif à des partenariats technologiques externes — l'université et le cadre GET 409 peuvent être un point d'entrée légitime pour un pilote sur une ligne
- Une solution offline-first basée sur des estimations probabilistes (horaires historiques + crowdsourcing) peut fonctionner sans GPS embarqué et livrer une valeur réelle dès le MVP

---

## 💚 Chapeau Vert — Créativité & Idées

- **Conducteur comme nœud de données** : le chauffeur confirme son départ de terminus via un simple SMS ou USSD — l'heure estimée est calculée côté serveur et diffusée aux usagers à l'arrêt, sans GPS
- **Réseau de sentinelles** : les usagers fréquents (comme Moussa) signalent le passage du bus en un tap — système de crowdsourcing de position minimal, fonctionnel en 2G
- **Notification SMS proactive** : l'usager s'abonne à son arrêt et reçoit un SMS *"Bus ligne X dans ~8 min"* — zéro application, zéro data, compatible feature phones

---

## 💙 Chapeau Bleu — Processus & Organisation

- La priorité immédiate est de valider la source de données : GPS embarqué DDD, crowdsourcing usagers, ou données conducteur — le reste de l'architecture dépend de ce choix
- Il faut définir un périmètre de pilote resserré : une ligne, un sens, deux arrêts clés (ex. Guédiawaye → Plateau) pour tester et itérer vite avant la S3
- Le jury attend une progression S1→S2 documentée — chaque décision d'architecture doit être tracée dans le dépôt GitHub avec le contexte de la décision, pas seulement le code

---

## 🔵 Synthèse Chapeau Bleu

**HMW révisé :** Comment pourrions-nous permettre aux usagers des bus DDD de Dakar d'estimer fiablement l'heure d'arrivée de leur bus — même sans connexion stable — afin qu'ils puissent décider en toute autonomie d'attendre ou de prendre une alternative ?

**Risques prioritaires :**
1. Absence de données GPS côté DDD — la solution doit fonctionner sans dépendre de l'opérateur
2. Perte de confiance immédiate si l'ETA affichée est inexacte — la fiabilité perçue prime sur la précision technique

**Question ouverte :** Quelle est la source de données de position minimale viable — et qui, dans l'écosystème (conducteur, usager, CETUD), est prêt à la produire sans friction ?
