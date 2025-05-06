# BabyTrackDay

**BabyTrackDay** est une application simple pour suivre les activités quotidiennes d'un bébé, telles que les repas, les siestes, les changements de couche, et plus encore. Elle permet également de générer un lien partageable contenant les données saisies.

## Fonctionnalités

- **Suivi des activités** :
  - Enregistrement de la date, de l'heure de réveil, de l'heure et de la quantité du biberon.
  - Ajout des changements de couche avec indication de la présence de selles.
  - Suivi des siestes avec les heures de début et de fin.
  - Ajout des repas solides avec le type de nourriture et le poids consommé.
  - Sélection de la qualité de la journée.
  - Ajout de commentaires.

- **Résumé de la journée** :
  - Affichage d'un résumé des activités saisies.

- **Partage des données** :
  - Génération d'un lien contenant les données encodées en base64.
  - Chargement des données à partir d'un lien.

## Structure du projet

- **HTML** : Interface utilisateur simple et intuitive.
- **CSS** : Styles intégrés pour une mise en page claire et responsive.
- **JavaScript** : Gestion des interactions utilisateur et encodage/décodage des données.

## Utilisation

1. Ouvrez le fichier `bebe.html` dans un navigateur.
2. Remplissez les champs pour enregistrer les activités du bébé.
3. Cliquez sur **"Générer le lien"** pour obtenir un lien partageable.
4. Partagez ce lien ou utilisez-le pour recharger les données dans l'application.

## Exemple de lien généré

Un lien généré ressemblera à ceci :
bebe.html#eyJkIjoiMjAyNS0wNS0wNiIsInciOiIwODowMCIsImIiOiIwNzowMCIsIm1sIjoiMjEwIiwicSI6IjMiLCJjIjoic29waGllIiwiZGlhcGVycyI6W3sidGltZSI6IjA4OjAwIiwicG9vcCI6dHJ1ZX0seyJ0aW1lIjoiMTE6MzAiLCJwb29wIjp0cnVlfV0sIm5hcHMiOlt7InN0YXJ0IjoiMTA6MDAiLCJlbmQiOiIxMTozMCJ9XSwibWVhbHMiOlt7InRpbWUiOiIxMjowMCIsInR5cGUiOiJjb3VyZ2V0dGUgYm9ldWYiLCJ3ZWlnaHQiOiIxMjAifV19

## Structure des données JSON

Les données saisies dans l'application sont organisées sous forme d'un objet JSON. Cet objet est encodé en base64 pour être inclus dans l'URL générée. Voici la structure des données JSON utilisées :

```json
{
  "d": "2025-05-06",          // Date de la journée
  "w": "08:00",              // Heure de réveil
  "b": "07:00",              // Heure du biberon
  "ml": "210",               // Quantité bue (en ml)
  "q": "3",                  // Qualité de la journée (1 = Difficile, 2 = Moyenne, 3 = Bonne)
  "c": "Commentaire",        // Notes ou remarques
  "diapers": [               // Liste des changements de couche
    {
      "time": "08:00",       // Heure du changement
      "poop": true           // Présence de selles (true/false)
    }
  ],
  "naps": [                  // Liste des siestes
    {
      "start": "10:00",      // Heure de début
      "end": "11:30"         // Heure de fin
    }
  ],
  "meals": [                 // Liste des repas solides
    {
      "time": "12:00",       // Heure du repas
      "type": "Purée",       // Type de nourriture
      "weight": "120"        // Poids consommé (en grammes)
    }
  ]
}