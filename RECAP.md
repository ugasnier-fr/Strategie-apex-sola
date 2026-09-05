# Récap projet — Stratégie CD Sport (live timing V2)

## Contexte
Outil de stratégie course (fichier "V2", vraisemblablement Excel avec formules/macros)
utilisé par l'équipe CD Sport. Objectif : brancher un flux **live timing** dessus et
faire en sorte que le fichier connaisse le **numéro de voiture** pour auto-remplir
les écarts (gaps), positions, etc. avec un maximum d'infos automatisées.

Dépôt GitHub : `ugasnier-fr/strategie-apex-sola`
Branche de travail dédiée : `claude/v2-live-timing-setup-f3no9r`

## État actuel
- Le dépôt GitHub est **vide** (aucun commit) — le fichier "V2" n'a pas encore été
  déposé dedans.
- Le fichier "V2" existe uniquement en local sur le PC de l'utilisateur :
  `C:\Users\Toyger\OneDrive\03-2026\00-CD Sport\01 - Travail\Outils\04-Stratégie`
- Aucune analyse du fichier n'a encore pu être faite (pas d'accès au poste Windows
  ni au fichier lui-même depuis cette session cloud).

## Ce qui a été fait dans cette conversation
1. Question initiale de l'utilisateur : où placer le lien live timing dans le
   fichier V2, et le fichier sait-il utiliser le n° de voiture pour auto-remplir
   les gaps et récupérer un max d'infos automatiquement.
2. Vérification du dépôt local et distant → confirmé vide, aucun fichier disponible
   pour analyse.
3. Explication à l'utilisateur de la méthode pour déposer le fichier sur GitHub
   (upload via l'interface web GitHub, page "Quick setup" → lien
   "uploading an existing file", limite ~25 Mo pour l'upload web, alternative
   Git LFS si plus lourd).
4. **Le fichier n'a pas encore été uploadé** au moment de la rédaction de ce récap.

## Prochaines étapes (à reprendre dans la nouvelle conversation)
1. L'utilisateur dépose le fichier V2 sur GitHub (branche `main` ou directement
   sur `claude/v2-live-timing-setup-f3no9r`).
2. Une fois le fichier disponible, l'analyser pour comprendre :
   - sa structure (onglets, cellules, formules existantes) ;
   - s'il y a déjà une cellule/config pour le n° de voiture ;
   - comment sont calculés les gaps actuellement (formules manuelles vs liées à
     une source externe) ;
   - présence éventuelle de macros VBA / Power Query / connexions de données.
3. Déterminer le type de flux live timing utilisé par CD Sport (ex: Alkamel,
   RaceControl, MyLaps, TSL, export CSV/API, page web à scraper) — c'est
   déterminant pour la méthode d'intégration (Power Query web, VBA + API,
   copier-coller assisté, etc.).
4. Proposer et implémenter :
   - un emplacement dédié pour l'URL du live timing (cellule de config ou onglet
     "Paramètres") ;
   - un mécanisme de filtrage automatique sur le n° de voiture du utilisateur
     pour isoler sa ligne dans le flux ;
   - le calcul automatique des gaps (avant/arrière, leader) à partir du flux.
5. Committer les évolutions sur la branche `claude/v2-live-timing-setup-f3no9r`.

## Infos utiles
- Email utilisateur : ugasnier@gmail.com
- Chemin local du fichier : `C:\Users\Toyger\OneDrive\03-2026\00-CD Sport\01 - Travail\Outils\04-Stratégie`
- Format du fichier (Excel/macros ? Google Sheets ?) : **à confirmer**
- Source du live timing (URL/API/type de plateforme) : **à confirmer**
