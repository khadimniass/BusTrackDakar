# Value Proposition Canvas — OnTime DAKAR

## HMW Définitif

"Comment pourrions-nous permettre aux usagers des bus DDD de Dakar d'estimer fiablement l'heure d'arrivée de leur bus — même sans connexion stable — afin qu'ils puissent décider en toute autonomie d'attendre ou de prendre une alternative ?"

---

## 👤 Profil Client — Moussa

### 🔧 Jobs To Be Done
*(Source : Chapeau Blanc)*

- Estimer le temps d'attente avant de quitter son domicile à Guédiawaye pour ne pas rater son bus ni partir trop tôt *(Blanc — "ratio très faible qui explique structurellement les intervalles longs")*
- Décider en temps réel à l'arrêt : attendre le bus DDD ou basculer vers une alternative (jakarta, taxi) *(Blanc — "DDD ne couvre que 6 % de la demande — Moussa n'a souvent aucune alternative crédible")*
- S'informer sur la position du bus sans dépendre d'un ami déjà à bord *(Blanc — "système SMS DDDT abandonné — le besoin existe mais la solution doit être plus légère")*

---

### 😣 Pains
*(Sources : Chapeau Rouge + Chapeau Noir)*

- Honte professionnelle d'arriver en retard pour une cause hors de son contrôle *(Rouge — "Moussa ne cherche pas une appli, il cherche à ne plus avoir honte d'arriver en retard devant son supérieur")*
- Résignation ancrée qui masque une vraie attente de changement *(Rouge — "c'est comme ça ici — résignation masque une attente réelle")*
- Impossibilité de calculer une ETA fiable sans GPS embarqué sur les bus DDD *(Noir — "DDD ne dispose pas de GPS embarqué sur tous ses bus — toute solution dépend d'une instrumentation que l'équipe ne contrôle pas")*
- Coupure du service exactement aux heures de pointe à cause de la saturation réseau 3G *(Noir — "l'application tombera en panne exactement aux heures de pointe")*
- Perte de confiance immédiate si l'ETA affichée est inexacte *(Noir — "si la solution affiche une ETA inexacte, la perte de confiance sera immédiate et difficile à récupérer")*

---

### 🌟 Gains
*(Source : Chapeau Jaune)*

- Reprendre le pouvoir de décision sur son trajet — choisir d'attendre ou partir en connaissance de cause *(Jaune — "marché massif et captif : 250 000 usagers quotidiens")*
- Bénéficier d'un effet d'adoption immédiat par bouche-à-oreille dès que l'outil est fiable *(Jaune — "le premier outil fiable créera un effet wow immédiat")*
- Accéder à une valeur réelle dès le MVP sans GPS embarqué grâce aux estimations probabilistes *(Jaune — "solution offline-first basée sur horaires historiques + crowdsourcing peut fonctionner sans GPS")*

---

## 💡 Proposition de Valeur — BusTrackDakar

### 📦 Produits & Services
*(Source : Chapeau Vert)*

- Signal de départ terminus par SMS ou USSD envoyé par le conducteur — déclenche le calcul d'ETA côté serveur sans GPS *(Vert — "conducteur comme nœud de données")*
- Crowdsourcing de position — l'usager signale le passage du bus en un tap ou SMS depuis l'arrêt, en 2G *(Vert — "réseau de sentinelles")*
- Notification SMS proactive à l'abonné : "Bus ligne X dans ~8 min" — zéro application, zéro data, compatible feature phone *(Vert — "notification SMS proactive")*

---

### 💊 Pain Relievers
*(Source : Chapeau Noir — mitigations)*

- Pas de GPS embarqué disponible → ETA calculée depuis signal de départ terminus + horaires historiques, sans dépendre de DDD *(Noir — mitigation C1)*
- Connexion 3G instable aux heures de pointe → mode dégradé offline avec dernière estimation mise en cache et horodatée, affichée même sans réseau *(Noir — mitigation C2)*
- Risque de perte de confiance sur ETA inexacte → indicateur de fiabilité systématique ("estimé / confirmé / données anciennes") affiché avec chaque ETA, jamais une heure brute sans contexte *(Noir — mitigation C3)*

---

### 🎁 Gain Creators
*(Source : Chapeau Jaune + Chapeau Bleu)*

- 250 000 usagers quotidiens captifs → pilote sur une ligne suffit à démontrer l'impact à grande échelle sans généralisation prématurée *(Jaune)*
- Précédent DDDT prouve la réceptivité de DDD aux partenariats technologiques → cadre GET 409 / Swiss UMEF comme point d'entrée légitime pour un accord de pilote officiel *(Jaune)*
- Source de données minimale viable identifiée dès S3 → validation terrain semaine 1 avant tout développement, ce qui réduit le risque de construire sur une hypothèse fausse *(Bleu — "la priorité est de valider la source de données")*

---

## ✅ FIT Check
*(Source : Chapeau Bleu)*

**Combinaison synergique retenue :** Signal conducteur SMS/USSD + cache offline + indicateur de fiabilité — cette combinaison adresse simultanément les trois pains fonctionnels critiques (absence GPS, instabilité réseau, risque de confiance) sans dépendre d'une infrastructure que l'équipe ne contrôle pas.

**Pain Relievers sans Pain correspondant :** Aucun — FIT validé. Chaque Pain Reliever est directement tracé vers un pain identifié au Chapeau Noir.

**Éléments non tracés :** Aucun — l'ensemble des jobs, pains, gains, produits et relievers sont tracés vers un chapeau source explicite issu des données terrain du projet.

**Conclusion :** Le FIT est solide sur le plan logique — chaque composant de la proposition de valeur répond à un besoin documenté, mais il reste conditionnel à la validation de C1 (source de données alternative viable) : si aucun conducteur n'accepte de signaler son départ, le Pain Reliever central s'effondre et le VPC doit être reconstruit autour du crowdsourcing usagers comme source primaire.
