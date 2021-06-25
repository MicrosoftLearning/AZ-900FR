---
wts:
    title: '08 - Implémenter Azure Functions (5 minutes)'
    module: 'Module 03 : Décrire les solutions principales et les outils de gestion'
---
# 08 - Implémenter Azure Functions

Dans cette procédure pas à pas, nous allons créer une application de fonction pour afficher un message Hello en cas de requête HTTP. 

# Tâche 1 : Créer une application de fonction (5 minutes)

Dans cette tâche, nous allons créer une application de fonction.

1. Connectez-vous au [portail Azure](https://portal.azure.com).

1. Dans la zone de texte située en haut du portail **Rechercher des ressources, des services et des documents**, recherchez et sélectionnez **Application de fonction** puis, dans le panneau **Application de fonction**, cliquez sur **+ Ajouter, + Créer ou + Nouveau**.

1. Sous l’onglet **Bases** du panneau **Application de fonction**, spécifiez les paramètres suivants (remplacez **xxxx** dans le nom de la fonction par des lettres et des chiffres de façon à ce que le nom soit unique au monde et maintenez les valeurs par défaut de tous les autres paramètres) : 

    | Paramètres | Valeur |
    | -- | --|
    | Abonnement | le nom de votre abonnement Azure |
    | Groupe de ressources | le nom d’un nouveau groupe de ressources **myRGFunction** |
    | le nom de l’application de fonction | **fonction-xxxx** |
    | Publier | **Code** |
    | Pile d’exécution | **NET** |
    | Version | **3.1** |
    | Région | **USA Est** |
    | | |

    **Remarque** - Veillez à modifier la valeur **xxxx** pour créer un **nom d’application de fonction** unique

1. Cliquez sur **Examiner et créer** puis, après la validation, cliquez sur **Créer** pour commencer l’approvisionnement et le déploiement de votre nouvelle application de fonction Azure.

1. Attendez la notification indiquant que la ressource a bien été créée.

1. Revenez au panneau **Application de fonction**, cliquez sur **Actualiser** et vérifiez que l’application de fonction nouvellement créée a le statut **En cours d’exécution**. 

    ![Capture d’écran de la page Function App avec la nouvelle application de fonction.](../images/0701.png)

# Tâche 2 : Créer une fonction déclenchée par requête HTTP et la tester

Dans cette tâche, nous allons utiliser la fonction Webhook + API pour afficher un message en cas de requête HTTP. 

1. Dans le panneau **Application de fonction**, cliquez sur l’application de fonction nouvellement créée. 

1. Sur le panneau de l’application de fonction, dans la section **Fonctions**, cliquez sur **Fonctions** puis cliquez sur **+ Ajouter**.

    ![Capture d’écran de l’étape de choix d’un environnement de développement dans les fonctions Azure pour le volet Mise en route de dot net dans le portail Azure. Les éléments d’affichage pour créer une nouvelle fonction dans le portail sont mis en surbrillance. Les éléments en surbrillance sont le développement de l’application de fonction, l’ajout d’une nouvelle fonction dans le portail et le bouton Continuer.](../images/0702.png)

1. Dans la section **Sélectionner un modèle** de l’option **Ajouter une fonction**, cliquez sur **Déclencheur HTTP**, sous la section **Détails du modèle**, acceptez les paramètres par défaut, puis cliquez sur **Ajouter**.

1. Dans le panneau **HttpTrigger1**, dans la section **Développeur**, cliquez sur **Code + Test**. 

1. Sur le panneau **HttpTrigger1 \| Code + Test**, examinez le code généré automatiquement et notez que le code est conçu pour exécuter une requête HTTP et les informations du journal. Notez également que la fonction renvoie un message de type Hello avec un nom. 

    ![Capture d’écran du code de la fonction. Le message de type Hello est en surbrillance.](../images/0704.png)

1. Cliquez sur **Obtenir l’URL de la fonction** dans la partie supérieure de l’éditeur de fonctions. 

1. Assurez-vous que la valeur de la liste déroulante **Clé** est définie sur **Par défaut**, puis cliquez sur **Copier** pour copier l’URL de la fonction. 

    ![Capture d’écran du panneau Obtenir l’URL de la fonction dans l’éditeur de fonction du portail Azure. Les éléments d’affichage du bouton Obtenir l’URL de la fonction, de la liste déroulante Définir la clé et du bouton Copier l’URL sont en surbrillance pour indiquer comment obtenir et copier l’URL de la fonction depuis l’éditeur de fonction.](../images/0705.png)

1. Ouvrez un nouvel onglet de navigateur et collez l’URL de la fonction copiée dans la barre d’adresse de votre navigateur web. Lorsque la page sera demandée, la fonction s’exécutera. Notez le message renvoyé indiquant que la fonction nécessite un nom dans le corps de la demande.

    ![Capture d’écran du message Veuillez indiquer un nom.](../images/0706.png)

1. Ajoutez **&name=*yourname*** à la fin de l’URL.

    **Remarque** : Remplacez ***yourname*** par votre prénom. Par exemple, si vous vous appelez Cindy, l’URL finale ressemblera à `https://azfuncxxx.azurewebsites.net/api/HttpTrigger1?code=X9xx9999xXXXXX9x9xxxXX==&name=cindy`

    ![Capture d’écran d’une URL de fonction en surbrillance et d’un exemple de nom d’utilisateur ajouté dans la barre d’adresse d’un navigateur web. Le message de type Hello et le nom d’utilisateur sont également mis en surbrillance pour illustrer la sortie de la fonction dans la fenêtre principale du navigateur.](../images/0707.png)

1. Lorsque votre fonction s’exécute, chaque invocation est tracée. Pour afficher les traces dans le portail Azure, revenez sur **HttpTrigger1 \|** Panneau **Code + Test** et cliquez sur **Contrôler**.

    ![Capture d’écran d’un journal d’informations de traçage résultant de l’exécution de la fonction dans l’éditeur de fonction du portail Azure.](../images/0709.png) 

Félicitations ! Vous avez créé une application de fonction pour afficher un message Hello en cas de requête HTTP. 

**Remarque** : Pour éviter des coûts supplémentaires, vous pouvez supprimer ce groupe de ressources. Recherchez des groupes de ressources, cliquez sur votre groupe de ressources, puis sur **Supprimer le groupe de ressources**. Vérifiez le nom du groupe de ressources, puis cliquez sur **Supprimer**. Surveillez les **notifications** pour voir comment se déroule la suppression.
