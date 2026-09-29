# Contexte projet — Stratégie course CD Sport (fichier V2)

> Ce fichier est destiné à être placé directement dans le dossier contenant le
> fichier de stratégie, pour qu'une session Claude Code **locale** démarre
> avec tout le contexte nécessaire sans repasser par les explications.

## Qui / quoi
- Équipe : CD Sport (endurance / course auto).
- Utilisateur : ugasnier@gmail.com.
- Fichier concerné : la version **"V2"** de l'outil de stratégie course,
  situé dans :
  `C:\Users\Toyger\OneDrive\03-2026\00-CD Sport\01 - Travail\Outils\04-Stratégie`
- Format exact du fichier : **à confirmer** (Excel avec macros ? Google Sheets
  téléchargé ? autre ?).

## Objectifs de l'utilisateur (dans l'ordre où ils ont été exprimés)
1. **Live timing** : savoir où placer le lien/flux de live timing dans le
   fichier V2.
2. **Auto-remplissage** : vérifier si le fichier connaît déjà le **numéro de
   voiture** de l'utilisateur pour en déduire automatiquement les écarts
   (gaps avant/arrière, gap leader), positions, et récupérer un maximum
   d'infos de façon automatique depuis le live timing.
3. **Audit complet** : faire une passe exhaustive du fichier pour détecter
   toutes les **incohérences** (formules, références de cellules, unités,
   logique de stratégie) — en posant des questions à l'utilisateur dès qu'un
   point touche à un choix de stratégie plutôt que de deviner.

## Ce qui a été fait jusqu'ici (session cloud précédente)
- Aucune analyse du fichier n'a pu être faite : la session tournait dans un
  environnement cloud isolé (Claude Code sur le web), sans accès au disque
  Windows de l'utilisateur.
- Le dépôt GitHub `ugasnier-fr/strategie-apex-sola` (branche
  `claude/v2-live-timing-setup-f3no9r`) a été utilisé comme tentative de
  transfert du fichier, mais le fichier lui-même **n'y a jamais été déposé**
  (seul un `RECAP.md` de contexte a été poussé).
- L'utilisateur préfère finalement travailler **en local** (Claude Code
  installé sur son PC) plutôt que via GitHub, pour avoir un accès direct au
  fichier sans étape d'upload.

## Instructions pour la nouvelle session locale
1. Ouvrir/lire directement le fichier V2 dans ce dossier (accès disque local
   disponible ici, contrairement à la session cloud précédente).
2. Poser les questions de clarification suivantes **avant** de modifier quoi
   que ce soit, si les réponses ne sont pas évidentes à la lecture du fichier :
   - Quelle est la plateforme/source du live timing (Alkamel, RaceControl,
     MyLaps, TSL, autre) ? Est-ce une URL web, un export CSV, une API ?
   - Le n° de voiture est-il déjà saisi quelque part dans le fichier
     (cellule de config, onglet "Paramètres") ?
   - Que recouvre exactement "les gaps" pour l'utilisateur : écart au leader,
     écart à la voiture devant/derrière, intervalle au tour précédent ?
   - Y a-t-il des macros VBA, du Power Query, ou des connexions de données
     déjà en place dans le fichier ?
   - Quelles sont les règles de stratégie actuelles (seuils de relais,
     logique d'arrêts, priorités) à respecter/ne pas casser pendant l'audit ?
3. Faire une passe complète de vérification des incohérences :
   - formules (gaps, temps au tour, carburant/relais si présent) ;
   - références de cellules (liens cassés, plages mal définies, décalages) ;
   - unités et formats (temps, distances, pourcentages) ;
   - cohérence de la logique de stratégie elle-même par rapport aux règles
     confirmées par l'utilisateur.
4. Ne pas supposer une règle de stratégie ambiguë : demander avant d'agir.
5. Une fois le live timing et l'auto-remplissage implémentés, proposer un
   emplacement clair pour la config (URL du flux, n° de voiture) dans un
   onglet "Paramètres" dédié si le fichier n'en a pas déjà un.
