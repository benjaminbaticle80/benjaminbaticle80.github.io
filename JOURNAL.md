# Journal du projet — Site Benjamin Baticle

Ce fichier retrace la genèse et l'évolution du site coaching de Benjamin Baticle, les décisions prises au fil du travail collaboratif avec Claude, et les chantiers ouverts. Il complète `CLAUDE.md` (qui sert de briefing technique aux futures sessions Claude Code) en offrant la perspective historique et éditoriale.

---

## Vue d'ensemble

- **Site en ligne** : https://benjaminbaticle80.github.io
- **Dépôt** : https://github.com/benjaminbaticle80/benjaminbaticle80.github.io
- **Stack** : HTML statique pur, hébergé sur GitHub Pages, déploiement automatique sur push vers `main`
- **Pages actuelles** : `index.html` (accueil) et `prestations.html` (offres et tarifs)
- **Coordonnées** : 07 86 06 95 01 · benjamin.baticle80@gmail.com · Normandie / région Caen

---

## Choix initiaux du projet

- **Format** : page HTML standalone, pas de framework (pas de React, pas de build), tout inline pour faciliter la maintenance et la portabilité
- **Cible** : particuliers / cyclistes individuels — du cyclosportif débutant au coureur élite
- **Offre** : coaching professionnel + profilage physiologique par lactatémie (Lactate Plus)
- **Identité** : pas de nom d'entreprise, le nom propre Benjamin Baticle suffit
- **Ambiance visuelle** : énergie sportive, fond très sombre (`#0c0c0e`) avec accents orange brûlé (`#e8420a`) et orange clair (`#ff7a1a`)
- **Typographies** : Bebas Neue (titres et chiffres), Barlow (corps), Barlow Condensed (labels et boutons)
- **Tonalité éditoriale** : tutoiement systématique, ton honnête et pédagogique, vocabulaire technique préservé (LT1, LT2, VLaMax, CP, W′), pas d'emoji sauf exception (📞 dans le CTA téléphone)

---

## Structure des pages

### `index.html`
1. Nav (3 liens : À propos, Services, Prestations, Contact)
2. Hero — photo gravel encodée en base64, légende « UCI Gravel World Series 2026 — Turnhout »
3. Stats band — 4 chiffres clés
4. À propos — méthodologie, background scientifique, contraintes personnelles assumées
5. Services — 4 cartes (profilage, coaching, suivi adaptatif, bilan gratuit)
6. Contact — formulaire branché sur Formsubmit.co
7. Footer

### `prestations.html`
1. Nav + page header
2. Ligne d'audience (« Du cyclosportif au coureur élite »)
3. Pricing — 2 cartes (profilage 109€ / coaching 60€/mois)
4. Note « Les deux prestations sont indépendantes »
5. **Section « Dans le coaching, concrètement »** — 4 points + verbatim placeholder sur les gains attendus
6. **Section « Le calibrage par puissance critique »** — 3 concepts (CP, W′, courbe) + courbe SVG puissance-durée avec asymptote et zone W′ + 4 principes de calibrage
7. **Section « Ton coaching, piloté sur intervals.icu »** — 3 fonctionnalités illustrées (planification, suivi de charge, profil de puissance) avec captures encadrées d'un faux bandeau navigateur
8. Process — 4 étapes (étape 01 = appel découverte gratuit avec téléphone cliquable)
9. Final CTA — téléphone en bouton principal, formulaire en lien secondaire
10. Footer

---

## Décisions de positionnement clés

### Audience large assumée
Benjamin coache à la fois des **cyclosportifs** (lui-même y compris : UCI Gravel World Series, courses FSGT) et des **coureurs élite** (Lucas Leroux : DH/Enduro élite, top Open FFC route, FSGT 1). La méthode s'adapte au niveau, ce point est explicité dès le haut de la page Prestations.

### Séparation claire des deux prestations
- Le **test lactatémique à 109€** est ponctuel, optionnel, et **ne conditionne pas** l'accès au coaching
- Le **coaching à 60€/mois** inclut gratuitement le profilage par puissance critique (tests CP du sprint au record de l'heure)
- L'**appel découverte gratuit** de 20 minutes est la porte d'entrée principale — sans engagement, sans paiement

Cette séparation a été motivée par l'analyse des freins du prospect novice : le test à 109€ comme prérequis aurait été une barrière trop haute pour quelqu'un voulant juste discuter.

### Lieu du test
Le test physiologique se déroule **sur le vélo du client, sur home-trainer, dans le local de Benjamin** (pas sur ergomètre clinique, pas sur le terrain). Cette précision est répétée à plusieurs endroits pour cadrer les attentes.

### Outils techniques retenus
- **Hébergement** : GitHub Pages, dépôt public `benjaminbaticle80.github.io`
- **Formulaire** : Formsubmit.co (gratuit, transfère vers `benjamin.baticle80@gmail.com`, première soumission déclenche un email d'activation à confirmer)
- **Coaching opérationnel** : intervals.icu, avec WhatsApp intégré directement à la plateforme
- **Édition du code** : Claude Code Desktop (en remplacement du copier-coller manuel via l'éditeur GitHub web)

---

## Parcours du déploiement (écueils rencontrés)

1. **Création initiale** réussie sans souci, hébergement GitHub Pages activé
2. **Ajout de `prestations.html`** : le fichier était bien sur le dépôt mais GitHub Pages ne re-déployait plus automatiquement — résolu en forçant la source dans Settings → Pages (toggle Deploy from a branch → GitHub Actions → retour)
3. **Tirets cadratins à corriger** : une passe PowerShell pour remplacer tous les `—` par `-` dans les fichiers HTML
4. **Photo non affichée puis légende à harmoniser** : corrigée en ré-uploadant la photo en base64 avec la bonne légende
5. **Formulaire de contact** : initialement faux (juste un message JS), branché ensuite sur Formsubmit.co avec activation de la première soumission par email
6. **Passage à Claude Code Desktop** : pour éviter les frictions répétées du copier-coller dans l'éditeur GitHub web (notamment pour les fichiers volumineux comme `index.html` avec sa photo en base64). Configuration de la variable d'environnement `CLAUDE_CODE_GIT_BASH_PATH`, clonage du dépôt en local dans `C:\Users\benja\Projets\site-benjamin\`

---

## Frictions prospect identifiées et traitements en cours

### 1. Manque de preuve sociale
Aujourd'hui aucun témoignage ni chiffre de progression sur le site. **En cours** : Benjamin demande à ses coachés (dont Lucas Leroux) l'autorisation de communiquer. Format prévu : photo + nom + discipline + 2-3 phrases en italique + 1 chiffre mis en avant (ex. « +18W à la CP en 4 mois »). À insérer sur `prestations.html`, idéalement entre la carte coaching et la section CP.

### 2. Vocabulaire technique intimidant pour un novice
La page Prestations parle naturellement de LT1/LT2, VLaMax, CP, W′. Pour un cycliste qui découvre, c'est intimidant. **À faire** : section « Comment se déroule le test » pour rassurer, en réponse à une checklist (avant / pendant / après / sécurité / lieu) que Benjamin doit compléter.

### 3. Le test 109€ comme barrière d'entrée
**Traité** : repositionnement complet. Le test n'est plus la porte d'entrée. L'appel découverte gratuit est mis en avant dans la section Contact d'`index.html`, dans la première étape du process sur `prestations.html`, et dans le final CTA.

---

## Chantiers ouverts (à reprendre dans cet ordre)

### En attente de réponses de Benjamin

1. **Témoignages coachés** — autorisations + verbatims + un chiffre par personne
2. **Checklist « Comment se déroule le test »** — répondre aux points (lieu exact, à prendre, préparation, déroulé technique, après-test, durée, conditions de santé) pour rédiger la section
3. **Verbatim Q3 final** — remplacer le placeholder actuel sur les gains attendus selon l'investissement

### Modif `index.html` à pousser dès que possible

4. **Bloc Contact d'`index.html`** — remplacer la zone `<div class="contact-info">` actuelle par la nouvelle version qui met en avant l'appel découverte gratuit et le téléphone cliquable (le code complet est dans nos échanges, à intégrer via Claude Code)

### Améliorations éditoriales d'`index.html` à envisager

5. ~~**Hero tagline**~~ - livré (commit 8957ab3, 2026-05-29)
6. ~~**Paragraphe « Ma méthode »**~~ - livré (commit 8957ab3, 2026-05-29)
7. ~~**Carte « Test sur ton matériel »**~~ - livré (commit 8957ab3, 2026-05-29)
8. ~~**Service 01 « Profilage Lactatémique »**~~ - livré (commit 8957ab3, 2026-05-29)

---

## Conventions de travail à conserver

- **Tutoiement** partout
- **Pas d'emoji** sauf 📞 dans les CTA téléphone
- **Variables CSS** : utiliser les variables existantes (`--bg`, `--bg2`, `--card`, `--accent`, `--accent2`, `--light`, `--muted`, `--border`), ne pas introduire de nouvelles couleurs
- **Responsive** : breakpoints à 850px et 500px sur `prestations.html`, à 900px sur `index.html`
- **Images** : optimisées web (~1300px max, JPEG q85, sous 200 KB), nommées en minuscules avec tirets, stockées à la racine
- **Commits** : atomiques, un commit = une intention, message clair
- **Pas de framework** : préserver la simplicité HTML/CSS inline, le site doit rester pilotable directement à la main si nécessaire
- **Typographie** : aucun tiret cadratin (U+2014) dans le contenu HTML. On utilise le tiret classique (-) entouré d'espaces comme séparateur de phrase. Règle à appliquer à tout nouveau contenu rédigé.

---

## Pour la suite

Toute nouvelle session avec Claude Code Desktop dans le dossier `C:\Users\benja\Projets\site-benjamin\` lira automatiquement `CLAUDE.md` au démarrage et aura le contexte du projet. Ce `JOURNAL.md` sert de mémoire historique et peut être lu en complément pour retrouver le pourquoi des décisions.

À chaque chantier terminé, mettre à jour ce fichier en cochant les points livrés et en ajoutant les nouvelles décisions prises.
