Fonctionnalités :


Site Vitrine
Présentation de l’organisme
Page d’accueil, 
mission, 
valeur, 
contact
catalogue de Formations public
aperçu des type de formations disponible mais sans le détail
Recherche simple 
Gestion des comptes 
inscription / login
création de compte et auth
Espace Profil
pour consulter modifier ses info personnelles
Gestion d’adhésion (helloAsso)
Paiement et synchro du statut 
Espace formation 
Tableau de bord 
vu rapide des formations et vielles.
Création de formation
Interface pour les formateur afin de rentrer les détails des formations (présentiel/ visio, dates, description)
Calendrier Formateur
vue des formations planifiées
liste des inscription par formations
pour confirmer la présence ou non des adhérent au formations
Accès webinaire
Zone donnant accès au contenue du webinaire
Valeur ajouté
Veille personnaliser
l’adhérent choisit ses centre d'intérêt pour sa veille
Contact formateur
Accès à une liste de contact pour interagir avec les formateurs
Certifications
Génération de certification 
Système qui produit un document PDF avec les informations de suivi/présence, daté et nominatif
historique des certifications 	
pour retrouver ses certifications


I. Gestion des Adhésions & Accès Payant

Paiement (Source)
Utilisation de HelloAsso pour la transaction et la gestion de l'adhésion. 
Rôles WordPress
Création d'un rôle utilisateur dédié dans WordPress : Adhérent Payant. Le rôle par défaut sera "Adhérent" (gratuit/simple).
Synchronisation
Nécessité d'un mécanisme pour synchroniser le statut de paiement de HelloAsso vers WordPress.
Méthode d'Intégration
Webhook ou Script d'Export/Import Régulier :
1. Idéal : Si HelloAsso fournit un Webhook après paiement réussi, ce dernier doit déclencher une API (endpoint) sur WordPress pour créer l'utilisateur ou mettre à jour son rôle vers "Adhérent Payant".
2. Alternative : Mise en place d'un script CRON sur WordPress qui interroge régulièrement l'API d'HelloAsso (si disponible) ou importe un fichier d'export CSV pour mettre à jour la base utilisateur (vérification des e-mails).
Règles d'Accès
Les pages et contenus listés dans les US payantes (Veille, Certification, Webinaire, Annuaire) seront protégés par un plugin de gestion de rôles (ex: Membership Plugin) pour n'être accessibles qu'au rôle "Adhérent Payant".
Expiration
Gestion de la date de fin d'adhésion dans le profil utilisateur. Le système doit rétrograder automatiquement le rôle à "Adhérant" après expiration de la période payée (nécessite un autre CRON de vérification).




II. Espace de Création de Formation (Airtable)


Interface Saisie
Formulaire Airtable Intégré : Le Formateur utilise un Formulaire Airtable (limité aux champs pertinents) intégré dans son espace WordPress pour créer la formation. L'ID du Formateur WordPress doit être automatiquement capturé ou saisi.
Base de Données
Utilisation d’une Base Airtable 
Affichage (Frontend)
Les données d'Airtable doivent être récupérées et affichées sur le site WordPress via l'API Airtable (clef en lecture seule).
Fréquence de Mise à Jour
Mise en cache des données d'Airtable sur WordPress pour optimiser les performances. Actualisation du cache toutes les 5 à 15 minutes




