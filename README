# Workflow Job Automation avec n8n

## Objectif

Automatiser la récupération et le filtrage d'offres d'emploi depuis **Pôle Emploi / France Travail**, préparer un contenu HTML pour email, et garder en mémoire les offres déjà traitées.

Ce workflow est un projet **d’entraînement en JavaScript et automatisation**, combinant manipulation de JSON, API, et gestion de workflow.

---

## Stack technique

-   n8n : nodes Function, Set, Merge, Email
-   JavaScript pour traitement des données
-   API Pôle Emploi / France Travail
-   Airtable pour stocker les ID des offres et suivre les emails envoyés
-   SMTP pour l’envoi d’emails (self-hosted)

---

## Limitations / Notes importantes

1. **Actuellement limité à la France** : seules les offres de France Travail sont utilisées via l’API.
2. **Prompt IA simplifié** : pour le moment, le prompt est minimal car le workflow tourne sur peu de ressources, mais il peut être adapté pour des prompts plus complexes ou plus intelligents.
3. **Filtres flexibles** :
    - Les filtres sur l’expérience et la localisation peuvent être modifiés facilement.
    - Pour l’expérience, France Travail utilise des marquages tels que `S` (souhaitée), `E` (exigée), etc.
    - plus d'info sur l'api France Travail Offres [ici](https://francetravail.io/produits-partages/catalogue/offres-emploi/documentation#/api-reference/operations/recupererListeOffre) :
4. **Mémoire des offres** : Airtable est utilisé avec la structure suivante :
    - `id` : ID de l’offre (Pôle Emploi)
    - `Created at` : date d’enregistrement
    - `Source` : source de l’offre (ex : FT)
    - `emailed` : case à cocher si email envoyé
    - `RECORD_ID` : ID Airtable pour mettre à jour la bonne ligne
5. **Self-hosted** : le workflow est conçu pour être exécuté sur un serveur personnel. Certaines configurations (SMTP, clés API) doivent être adaptées si vous utilisez une instance cloud.
6. **Clé API** : le workflow nécessite une clé API France Travail. **Ne laissez jamais votre clé dans GitHub public**. Remplacez-la par la vôtre dans les credentials n8n.

---

## Installation / Utilisation

1. Cloner ou télécharger le dépôt.
2. Importer le fichier `workflow-job-search.json` dans n8n.
3. Configurer vos credentials :
    - API France Travail
    - SMTP pour l’envoi des emails
    - Airtable (facultatif, si vous voulez garder la trace des offres déjà traitées)
4. Exécuter le workflow pour récupérer et traiter les offres.

---

## Résultat attendu

-   JSON nettoyé des offres filtrées
-   Contenu HTML prêt à être envoyé par email
-   Stockage des IDs dans Airtable pour éviter les doublons

---

## Bonus

-   Capture d’écran du workflow n8n pour visualiser la logique
-   Possibilité d’ajouter d’autres filtres (type de contrat, télétravail, etc.)
-   Adaptable à d’autres sources d’offres ou d’autres agents IA
