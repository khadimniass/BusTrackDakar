## Backlog S3 — OnTime DAKAR

### HMW Définitif

"Comment pourrions-nous permettre aux usagers des bus DDD de Dakar d'estimer fiablement l'heure d'arrivée de leur bus — même sans connexion stable — afin qu'ils puissent décider en toute autonomie d'attendre ou de prendre une alternative ?"

---

### User Stories MUST

*(À construire obligatoirement en S3)*

#### US-01

**Story :** En tant que conducteur DDD sur la ligne pilote, je veux envoyer un SMS ou composer un code USSD au départ du terminus afin de déclencher le calcul d'ETA pour les usagers en attente.

**Priorité :** MUST

**Outil :** Dify (workflow de réception SMS + calcul ETA) + SMS API (Twilio ou Orange Sénégal API)

**Effort :** Moyen

**Adresse :** Pain Reliever 1 — ETA calculée depuis signal terminus + historiques, sans GPS DDD

**Critère d'acceptation :** Un SMS envoyé depuis un téléphone test au numéro pilote déclenche dans Dify un workflow qui calcule une ETA et la stocke — vérifiable dans les logs Dify dans les 10 secondes suivant l'envoi.

---

#### US-02

**Story :** En tant que Moussa, usager à l'arrêt de Guédiawaye, je veux recevoir un SMS avec l'heure estimée d'arrivée de mon bus et un indicateur de fiabilité afin de décider si j'attends ou si je prends un jakarta.

**Priorité :** MUST

**Outil :** Dify (génération du message ETA + label fiabilité) + SMS API sortant

**Effort :** Moyen

**Adresse :** Pain Reliever 3 — indicateur de fiabilité systématique ("estimé / confirmé / données anciennes")

**Critère d'acceptation :** Après déclenchement US-01, un SMS du type "Bus ligne X dans ~12 min — estimé" est reçu sur un téléphone abonné dans les 15 secondes, sans intervention manuelle de l'équipe.

---

#### US-03

**Story :** En tant que Moussa, je veux accéder à la dernière ETA connue même quand mon réseau est coupé afin de ne pas me retrouver sans information aux heures de pointe.

**Priorité :** MUST

**Outil :** Bolt.new (PWA avec cache localStorage) + Dify (endpoint ETA)

**Effort :** Moyen

**Adresse :** Pain Reliever 2 — mode dégradé offline, dernière estimation mise en cache et horodatée

**Critère d'acceptation :** Sur le navigateur mobile en mode avion, la PWA affiche la dernière ETA reçue avec son horodatage ("Dernière mise à jour : 07h34") — sans rechargement réseau, vérifiable en coupant le WiFi du téléphone test.

---

### User Stories SHOULD

*(À construire si le temps le permet)*

#### US-04

**Story :** En tant que Moussa, je veux signaler en un tap sur la PWA que je viens de voir passer le bus afin d'améliorer la fiabilité de l'ETA pour les usagers suivants.

**Priorité :** SHOULD

**Outil :** Bolt.new (bouton "J'ai vu le bus") + Dify (workflow crowdsourcing — mise à jour position estimée)

**Effort :** Moyen

**Adresse :** Gain Creator — valeur réelle dès le MVP via crowdsourcing usagers sans GPS

**Critère d'acceptation :** Le tap envoie un timestamp et l'identifiant de l'arrêt à Dify, qui recalcule l'ETA pour les abonnés en aval — vérifiable dans les logs Dify dans les 5 secondes.

---

#### US-05

**Story :** En tant que Moussa, je veux m'abonner à mon arrêt habituel en une seule action afin de recevoir automatiquement les ETAs chaque matin sans redemander.

**Priorité :** SHOULD

**Outil :** Dify (gestion abonnements par numéro de téléphone) + SMS API

**Effort :** Faible

**Adresse :** Gain Creator — adoption organique et réduction de la friction quotidienne

**Critère d'acceptation :** Un SMS "ABONNER GUEDIAWAYE" enregistre le numéro dans Dify et déclenche un envoi automatique dès le prochain signal conducteur — aucune action supplémentaire requise de l'usager.

---

### User Stories COULD

*(Roadmap post-MVP)*

#### US-06

**Story :** En tant que Moussa, je veux recevoir les messages en wolof afin de comprendre l'information sans effort de traduction mentale.

**Priorité :** COULD

**Outil :** Dify (prompt multilingue FR/WO)

**Effort :** Faible

**Adresse :** Gain Creator post-MVP — adoption non-francophone

**Critère d'acceptation :** Le message SMS est rendu en wolof correct et compréhensible par 4 locuteurs natifs sur 5 testés.

---

#### US-07

**Story :** En tant que Moussa, je veux voir sur une carte légère la position approximative du bus afin d'avoir une représentation visuelle de l'attente.

**Priorité :** COULD

**Outil :** Bolt.new (carte Leaflet.js minimaliste)

**Effort :** Élevé

**Adresse :** Gain Creator post-MVP — visualisation spatiale

**Critère d'acceptation :** La carte charge en moins de 4 secondes sur 3G à 1 Mbit/s simulé et affiche un marqueur de position estimée du bus sans GPS exact.

---

#### US-08

**Story :** En tant que responsable impact, je veux consulter un tableau de bord avec le taux de retour, la précision ETA et le volume de signaux conducteurs afin de présenter les métriques à la démo S6.

**Priorité :** COULD

**Outil :** Dify (logs) + Bolt.new (dashboard lecture seule)

**Effort :** Moyen

**Adresse :** Métrique Nord + Tableau de Bord S6

**Critère d'acceptation :** Le dashboard affiche en temps réel les 3 métriques définies dans metriques-succes.md avec valeur réelle vs cible.

---

### Sprint S3

**Semaine 1 :** US-01 + US-02 — mettre en place le pipeline complet signal conducteur → calcul ETA → SMS sortant sur Dify ; valider en conditions réelles au terminus de Guédiawaye (hypothèse C1 et C2 simultanément).

**Semaine 2 :** US-03 — intégrer la PWA Bolt.new avec cache offline et connecter l'endpoint ETA Dify ; tester le mode dégradé sur le terrain avec un téléphone Android entrée de gamme en 3G réelle.

**Démo S6 :** Démontrer en live US-01 + US-02 + US-03 — un membre de l'équipe envoie le SMS de départ terminus, un second reçoit l'ETA sur son téléphone en 15 secondes, un troisième coupe le réseau et montre la dernière ETA en cache sur la PWA.
