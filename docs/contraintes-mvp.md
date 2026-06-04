## Contraintes MVP — OnTime DAKAR

### Persona

Moussa · 28 ans · Employé de bureau au Plateau · Guédiawaye, Dakar, Sénégal · Smartphone Android entrée de gamme — connexion 3G intermittente

---

### Contraintes Non Négociables

#### Contrainte 1

**Critère :** Le MVP DOIT fonctionner en mode dégradé (offline ou bas débit) et afficher la dernière estimation connue avec son horodatage, même sans connexion active.

**Origine :** Chapeau Noir

**Élimine :** Toute architecture temps réel pur (WebSocket, streaming GPS live) — si la donnée ne peut pas être mise en cache et servie offline, la fonctionnalité est hors scope MVP.

---

#### Contrainte 2

**Critère :** Le MVP NE DOIT PAS dépendre d'un flux GPS fourni par DDD pour calculer une ETA — il doit pouvoir estimer la position du bus à partir de données alternatives (horaires historiques, crowdsourcing usagers, signal conducteur).

**Origine :** Chapeau Noir + Chapeau Blanc

**Élimine :** Toute intégration API avec le système d'information de DDD, tout module de tracking embarqué nécessitant un accord opérateur préalable.

---

#### Contrainte 3

**Critère :** Le MVP DOIT afficher une ETA avec un indicateur explicite de fiabilité (ex. "estimé", "confirmé", "données anciennes") — jamais une heure sans contexte de confiance.

**Origine :** Chapeau Noir

**Élimine :** Un simple affichage d'heure brute sans marge d'incertitude — afficher "07h34" sans contexte est pire que de ne rien afficher si l'estimation est fausse.

---

#### Contrainte 4

**Critère :** Le MVP DOIT être accessible sans installation d'application native — via SMS, USSD, ou navigateur mobile léger (PWA) compatible Android entrée de gamme.

**Origine :** Chapeau Blanc

**Élimine :** Application native iOS/Android à télécharger, onboarding avec création de compte, toute dépendance à un store (Play Store, App Store).

---

#### Contrainte 5

**Critère :** Le MVP NE DOIT PAS couvrir plus d'une ligne pilote et deux arrêts clés (Guédiawaye → Plateau) lors de la première itération.

**Origine :** Chapeau Blanc

**Élimine :** Couverture multi-lignes, carte interactive du réseau complet DDD, moteur de calcul d'itinéraires — le ratio 100 bus / 24 lignes rend toute généralisation prématurée sans données de terrain validées.

---

#### Contrainte 6

**Critère :** Le MVP DOIT produire une estimation en moins de 3 secondes sur une connexion 3G à 1 Mbit/s simulée.

**Origine :** Chapeau Noir

**Élimine :** Tout traitement lourd côté client (calcul d'itinéraire, rendu cartographique vectoriel, ML on-device) — la contrainte réseau impose que la logique soit côté serveur et la réponse minimaliste.

---

### Fonctionnalités Éliminées

- **Tracking GPS temps réel** → éliminé parce que DDD ne fournit pas de flux GPS fiable et que l'architecture dépendante d'un opérateur est hors du contrôle de l'équipe
- **Application native (APK)** → éliminée parce que Moussa n'a pas nécessairement l'espace disque, le forfait data, ni le réflexe d'installation — le canal SMS/USSD a zéro friction
- **Couverture réseau complète (24 lignes)** → éliminée parce que le volume de données à collecter et valider dépasse le scope d'un MVP et dilue la fiabilité perçue
- **Carte interactive temps réel** → éliminée parce qu'elle est gourmande en data, inutilisable hors connexion, et ne répond pas au besoin core de Moussa qui est une ETA, pas une carte
- **Compte utilisateur et historique personnel** → éliminé parce qu'il introduit une friction à l'entrée sans valeur ajoutée au stade MVP — l'anonymat est un avantage en contexte de confiance numérique fragile
- **Notifications push** → éliminées parce qu'elles nécessitent une app native installée et une connexion stable — incompatibles avec les contraintes réseau et équipement de Moussa
- **Multilingue (wolof, français, anglais)** → reporté post-MVP parce que la priorité est de valider la fiabilité de l'ETA avant de travailler l'expérience linguistique

---

### Critère de Validation Final

Le MVP est valide si et seulement si : Moussa, depuis un arrêt de Guédiawaye avec une connexion 3G instable, obtient en moins de 3 secondes une estimation d'arrivée de son bus DDD accompagnée d'un indicateur de fiabilité — sans installer d'application et sans compte utilisateur.

