Nous avons développé un système de clavardage en Java permettant une communication en temps réel, répondant aux exigences du projet grâce à une gestion des threads pour les connexions simultanées et la persistance des messages dans un fichier texte, sans utiliser de bibliothèques externes.

1. **Fonctionnement côté client :**
 - À l'ouverture, le client saisit l'adresse IP et le port du serveur pour établir la connexion.
 - Utilisation de `DataInputStream` et `DataOutputStream` pour la communication.
 - Authentification de l'utilisateur, avec possibilité de créer un compte automatiquement si non existant.
 - Utilisation de threads pour permettre l'envoi et la réception simultanés de messages, avec une gestion des erreurs et une limite de 200 caractères par message.
 - Commande `exit` pour quitter l'application.

2. **Fonctionnement côté serveur :**
 - À son démarrage, l'utilisateur configure l'adresse IP et le port d'écoute.
 - Chaque nouvelle connexion client déclenche la création d'une instance `ClientHandler` sur un nouveau thread pour gérer les communications sur des sockets distincts.
 - Gestion des threads pour les connexions multiples, vérification des informations d'identification et persistance des messages dans un fichier texte.
 - Affichage des 15 derniers messages de l'historique de clavardage.
 - Les données utilisateur et l'historique de clavardage sont enregistrés dans un fichier texte pour maintenir les profils des utilisateurs et l'historique des messages même après redémarrage du serveur.
