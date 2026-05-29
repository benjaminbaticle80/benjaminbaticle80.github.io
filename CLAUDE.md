# Projet : site Benjamin Baticle — coaching cyclisme & profilage physiologique

Ce fichier sert de mémoire de projet pour toute session Claude Code. Lis-le au démarrage.

---

## Contexte

- **Site** : [https://benjaminbaticle80.github.io](https://benjaminbaticle80.github.io)  
- **Dépôt** : [https://github.com/benjaminbaticle80/benjaminbaticle80.github.io](https://github.com/benjaminbaticle80/benjaminbaticle80.github.io)  
- **Hébergement** : GitHub Pages (déploiement automatique sur push vers `main`)  
- **Stack** : HTML statique pur (pas de framework, pas de build). Tout est inline (CSS et SVG dans le HTML).  
- **Fichiers actifs à la racine** :  
  - `index.html` — page d'accueil (hero, à propos, services, contact)  
  - `prestations.html` — prestations et tarifs détaillés  
  - `intervals-planification.jpg`, `intervals-charge.jpg`, `intervals-puissance.jpg` — captures intervals.icu utilisées dans `prestations.html`

---

## Qui est Benjamin Baticle

- Ingénieur AgroParisTech \+ BTSA analyses biologiques  
- Coach cycliste, basé en Normandie (région de Caen)  
- Cyclosportif lui-même (UCI Gravel World Series, FSGT)  
- Coachés du cyclosportif débutant à l'élite (ex. Lucas Leroux : DH/Enduro élite, top Open FFC route, FSGT 1\)  
- Téléphone : **07 86 06 95 01**  
- Email : [**benjamin.baticle80@gmail.com**](mailto:benjamin.baticle80@gmail.com)

## Offre commerciale

1. **Profilage lactatémique complet — 109€ / test ponctuel**  
     
   - Test au Lactate Plus, paliers de 8 min  
   - Sur son propre vélo, sur home-trainer dans le local de Benjamin  
   - Détermination LT1, LT2, VLaMax, profil métabolique  
   - Restitution avec zones et séances types

   

2. **Coaching cyclisme personnalisé — 60€ / mois, sans engagement**  
     
   - Plateforme : **intervals.icu** (avec WhatsApp intégré)  
   - Plan d'entraînement personnalisé  
   - Profilage par puissance critique inclus (CP \+ W′, tests du sprint au record de l'heure)  
   - Débrief après chaque séance (recommandé)  
   - Recalibrage permanent selon retours et performance

**Important** : les deux prestations sont indépendantes. Le coaching ne nécessite PAS d'avoir fait le test lactatémique. Le profilage CP est inclus dans le coaching, gratuit.

**Point d'entrée privilégié** : un appel découverte gratuit de 20 min (téléphone ou visio), sans engagement, sans paiement.

---

## Système de design

### Couleurs (CSS variables — déjà définies dans chaque page)

\--bg:        \#0c0c0e   /\* fond principal sombre \*/

\--bg2:       \#111115   /\* fond secondaire (sections alternées) \*/

\--card:      \#16161c   /\* cartes / blocs \*/

\--accent:    \#e8420a   /\* orange brûlé (accent principal) \*/

\--accent2:   \#ff7a1a   /\* orange clair (accent secondaire) \*/

\--light:     \#f0ede8   /\* texte principal \*/

\--muted:     \#7a7880   /\* texte secondaire / labels \*/

\--border:    rgba(255,255,255,0.07)

### Typographie (Google Fonts, déjà importées)

- **Bebas Neue** — titres, chiffres en gros, accents (letter-spacing 0.03-0.12em)  
- **Barlow** — corps de texte, weight 300/400/600  
- **Barlow Condensed** — labels, tags, eyebrows, boutons (uppercase, letter-spacing 0.15-0.3em)

### Tonalité éditoriale

- **Tutoiement** systématique (« tu », « toi », « ton vélo »)  
- Pas d'emoji dans les textes (sauf rares exceptions : 📞 dans CTA téléphone)  
- Honnête et précis : pas de promesses gonflées, pas de superlatifs vides  
- Pédagogique : on explique les concepts physiologiques (CP, W′, LT1/LT2) en restant accessible  
- Vocabulaire spécifique préservé : LT1, LT2, VLaMax, CP, W′, puissance critique, FTP
- **Typographie** : aucun tiret cadratin (U+2014) dans le contenu HTML. On utilise toujours le tiret classique (-) entouré d'espaces s'il sert de séparateur de phrase. Cette règle s'applique à tout nouveau contenu rédigé.

---

## État au dernier commit

`prestations.html` contient les sections suivantes dans l'ordre :

1. NAV \+ PAGE HEADER  
2. PRICING (2 cartes : profilage 109€, coaching 60€/mois) avec note « prestations indépendantes »  
3. DAILY COACHING (« Dans le coaching, concrètement ») — 4 points \+ verbatim sur les gains  
4. CRITICAL POWER CALIBRATION — 3 concepts (CP, W′, courbe) \+ courbe SVG puissance-durée \+ 4 principes de calibrage  
5. INTERVALS.ICU SHOWCASE — 3 fonctionnalités illustrées (planification, charge, puissance)  
6. PROCESS (4 étapes) — étape 01 \= « Appel découverte » avec téléphone cliquable  
7. FINAL CTA — téléphone en bouton principal \+ formulaire en lien secondaire  
8. FOOTER

`index.html` contient les sections suivantes :

1. NAV (avec lien vers `prestations.html`)  
2. HERO (photo gravel, légende « UCI Gravel World Series 2026 — Turnhout »)  
3. STATS BAND  
4. À PROPOS — méthodologie et background  
5. SERVICES — 4 cartes  
6. CONTACT — formulaire branché sur Formsubmit.co vers [benjamin.baticle80@gmail.com](mailto:benjamin.baticle80@gmail.com)

---

## Chantiers en cours / à venir (par priorité)

### En attente de réponses de Benjamin

1. **Section témoignages** — Benjamin demande à 2-3 coachés (dont Lucas Leroux) l'autorisation de communiquer. Quand il aura les accords \+ un chiffre concret par personne, créer une section dédiée sur `prestations.html` (avant la section CP, ou entre coaching et CP). Format proposé : photo \+ nom \+ discipline \+ 2-3 phrases en italique \+ 1 chiffre mis en avant (ex. « \+18W à la CP en 4 mois »).  
     
2. **Section « Comment se déroule le test »** — pour rassurer les prospects novices avant d'investir 109€. Benjamin doit fournir les réponses à une checklist (avant / pendant / après / déroulé / sécurité / lieu). À insérer probablement à la fin de la section CP calibrage ou dans une section dédiée juste avant le process.  
     
3. **Verbatim Q3 final** — actuellement un placeholder dans la section DAILY COACHING (« Les gains dépendent de ton investissement... »). À remplacer par le verbatim définitif de Benjamin quand il l'aura rédigé.

### Modifs à pousser dès que possible

4. **Bloc Contact d'`index.html`** — à harmoniser pour mettre en avant l'appel découverte gratuit avec le numéro 07 86 06 95 01 cliquable. Le nouveau bloc HTML (déjà rédigé dans nos échanges) doit remplacer le `<div class="contact-info">...</div>` actuel.

### Améliorations éditoriales d'`index.html` à envisager

5. **Hero tagline** — clarifier que la puissance critique est dans le coaching, pas dans le test ponctuel  
6. **Paragraphe « À propos / Ma méthode »** — préciser « home-trainer dans mon local » et la séparation lactatémie (test) / puissance critique (coaching)  
7. **Carte À propos 03 « Test sur ton matériel »** — corriger « home-trainer ou sur le terrain » en « home-trainer dans mon local »  
8. **Service 01 « Profilage Lactatémique »** — retirer les mentions de puissance critique (déplacées dans le coaching) ; remplacer le tag « Sprint → 1h » par « Sur home-trainer »

---

## Conventions de travail

- **Commits clairs et atomiques** : un commit \= une intention (« Add testimonials section », « Update contact block to feature phone CTA », etc.) avec message en anglais court ou en français court.  
- **Pas de fichier de build, pas de framework** : tout reste en HTML/CSS/JS inline. Préserver cette simplicité.  
- **Respecter le design system** : utiliser les variables CSS existantes, ne pas introduire de nouvelles couleurs. Garder la cohérence typographique.  
- **Responsive** : le site est déjà responsive (breakpoints 850px et 500px sur prestations, 900px sur index). Toute nouvelle section doit avoir ses règles responsive.  
- **Images** : optimisées pour le web (\~1300px de large max, JPEG q85, taille sous 200 KB). Stockées à la racine, référencées par nom relatif.

---

## Formulaire de contact (Formsubmit.co)

- Action : `https://formsubmit.co/benjamin.baticle80@gmail.com`  
- Méthode POST  
- Champs hidden : `_subject`, `_captcha=false`, `_template=table`, `_next` (URL de retour avec `?envoyé=1`)  
- Bannière JS de confirmation après envoi (déjà en place dans `index.html`)  
- **Note** : la première soumission par utilisateur déclenche un email d'activation depuis Formsubmit qu'il faut valider.

---

## En cas de doute

Demande à Benjamin avant de toucher à :

- La photo du hero (encodée en base64 dans `index.html`)  
- L'adresse email ou le numéro de téléphone  
- La structure tarifaire ou les prix  
- La tonalité éditoriale (tutoiement, pédagogie)

