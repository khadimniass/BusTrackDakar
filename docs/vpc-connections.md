## Connexions 6 Chapeaux → VPC — OnTime DAKAR

### Profil Client — Origines

#### Jobs To Be Done

| Job | Chapeau d'origine | Citation exacte |
|---|---|---|
| Estimer le temps d'attente avant de quitter Guédiawaye | Chapeau Blanc | "ratio très faible qui explique structurellement les intervalles longs entre passages" |
| Décider à l'arrêt : attendre ou basculer vers une alternative | Chapeau Blanc | "DDD ne couvre que 6 % de la demande — Moussa n'a souvent aucune alternative crédible" |
| S'informer sans dépendre d'un ami déjà à bord | Chapeau Blanc | "système SMS DDDT abandonné — le besoin existe mais la solution doit être plus légère" |

#### Pains

| Pain | Chapeau d'origine | Citation exacte |
|---|---|---|
| Honte professionnelle d'arriver en retard | Chapeau Rouge | "Moussa ne cherche pas une appli, il cherche à ne plus avoir honte d'arriver en retard" |
| Résignation ancrée masquant une attente de changement | Chapeau Rouge | "c'est comme ça ici — résignation masque une attente réelle de changement" |
| Impossibilité de calculer une ETA sans GPS embarqué | Chapeau Noir | "DDD ne dispose pas de GPS embarqué — toute solution dépend d'une instrumentation que l'équipe ne contrôle pas" |
| Coupure de service aux heures de pointe (réseau 3G saturé) | Chapeau Noir | "l'application tombera en panne exactement aux heures de pointe" |
| Perte de confiance immédiate sur ETA inexacte | Chapeau Noir | "si la solution affiche une ETA inexacte, la perte de confiance sera immédiate et difficile à récupérer" |

#### Gains

| Gain | Chapeau d'origine | Citation exacte |
|---|---|---|
| Reprendre le pouvoir de décision sur son trajet | Chapeau Jaune | "250 000 usagers quotidiens — même une adoption partielle représente un impact à grande échelle" |
| Adoption par bouche-à-oreille dès que l'outil est fiable | Chapeau Jaune | "le premier outil fiable créera un effet wow immédiat et une adoption rapide par bouche-à-oreille" |
| Valeur réelle dès le MVP sans GPS grâce aux estimations probabilistes | Chapeau Jaune | "solution offline-first basée sur horaires historiques + crowdsourcing peut fonctionner sans GPS" |

---

### Proposition de Valeur — Origines

#### Pain Relievers

| Pain Reliever | Pain adressé | Chapeau d'origine |
|---|---|---|
| ETA calculée depuis signal terminus + historiques, sans GPS DDD | Impossibilité de calculer une ETA sans GPS embarqué | Chapeau Noir → Chapeau Vert |
| Mode dégradé offline — dernière estimation mise en cache et horodatée | Coupure de service aux heures de pointe | Chapeau Noir → Chapeau Bleu |
| Indicateur de fiabilité systématique ("estimé / confirmé / données anciennes") | Perte de confiance immédiate sur ETA inexacte | Chapeau Noir → Chapeau Bleu |

#### Gain Creators

| Gain Creator | Gain adressé | Chapeau d'origine |
|---|---|---|
| Pilote ligne unique — démontre l'impact sans généralisation prématurée | Adoption à grande échelle (250 000 usagers) | Chapeau Jaune |
| Cadre GET 409 / Swiss UMEF comme point d'entrée pour accord pilote DDD | Bouche-à-oreille et légitimité institutionnelle | Chapeau Jaune |
| Validation source de données semaine 1 avant tout développement | Valeur réelle dès le MVP sans GPS | Chapeau Bleu |

---

### Éléments Non Tracés

Aucun — tous les éléments du VPC sont tracés vers au moins un chapeau source explicite issu des sessions 6 Chapeaux de Bono du projet BusTrackDakar.

---

### Synthèse de Cohérence

**Alignement :** Fort — chaque job, pain et gain du profil client trouve sa réponse dans la proposition de valeur, et chaque composant de la proposition est ancré dans un chapeau documenté. Le FIT logique est complet.

**Tension principale :** Le Pain Reliever central (ETA sans GPS via signal conducteur) repose entièrement sur la coopération volontaire d'un tiers — le conducteur DDD — dont le comportement n'a pas encore été validé sur le terrain, ce qui crée une dépendance critique non maîtrisée entre la solidité du VPC et le résultat de l'hypothèse C1.

**Recommandation avant S3 :** Aller au terminus de Guédiawaye dès la semaine 1 de S3 pour tester en conditions réelles si un conducteur accepte d'envoyer un SMS de départ — si le résultat est négatif, recentrer immédiatement la source de données sur le crowdsourcing usagers (sentinelles) et mettre à jour vpc.md et contraintes-mvp.md en conséquence avant la fin de la semaine.
