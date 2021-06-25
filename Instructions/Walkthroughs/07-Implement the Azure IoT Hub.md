---
wts:
    title: '07 - Implémenter Azure IoT Hub (10 minutes)'
    module: 'Module 03 : Décrire les solutions principales et les outils de gestion'
---
# 07 - Implémenter Azure IoT Hub

Dans cette procédure pas à pas, nous allons configurer un nouveau hub IoT Azure dans le portail Azure, puis authentifier une connexion à un appareil IoT à l’aide du simulateur d’appareil Raspberry Pi en ligne. Les données et les messages des capteurs sont transmis du simulateur Raspberry Pi à votre hub IoT Azure. Vous pouvez afficher des mesures pour l’activité de messagerie dans le portail Azure.

# Tâche 1 : Créer une ressource IoT Hub (10 minutes)

Dans cette tâche, nous allons créer un hub IoT. 

1. Connectez-vous au [portail Azure](https://portal.azure.com).

2. Dans le panneau **Tous les services**, recherchez et sélectionnez **Comptes de stockage**, puis cliquez sur **+ Ajouter, + Créer ou + Nouveau**.

3. Sous l’onglet **Général** du panneau **Hub IoT**, remplissez les champs avec les détails suivants (remplacez **xxxx** dans le nom du compte de stockage par des lettres et des chiffres, de façon à ce que le nom soit unique au monde) :

    | Paramètres | Valeur |
    |--|--|
    | Abonnement | **Choisir votre abonnement** |
    | Groupe de ressources |  **myRGIoT** (créer un nouveau)|
    | Région | **USA Est** |
    | Nom du hub IoT | **my-hub-groupxxxx** |
    | | |

    **Remarque** - Veillez à modifier la valeur **xxxx** pour créer un **Nom de Hub IoT** unique.

4. Accédez à l’onglet **Gestion** et définissez la valeur de **Tarification et niveau d’échelle** sur **S1 : Niveau standard**.

5. Cliquez sur le bouton **Examiner et créer**.

6. Cliquez sur le bouton **Créer** pour commencer à créer votre nouvelle instance hub IoT Azure.

7. Attendez que l’instance hub IoT Azure soit déployée. 

# Tâche 2 : Ajouter un appareil IoT

Dans cette tâche, nous allons ajouter un appareil IoT au hub IoT. 

1. Une fois le déploiement terminé, cliquez sur **Accéder à la ressource** dans le panneau de déploiement. Une autre solution consiste, à partir du panneau **Tous les services**, à rechercher et sélectionner **hub IoT** et à localiser votre nouvelle instance hub IoT

	![Capture d’écran des notifications de déploiement en cours et de déploiement réussi dans le portail Azure.](../images/0601.png)

2. Pour ajouter un nouvel appareil IoT, faites défiler vers la bas jusqu’à la section **Explorateurs**, puis cliquez sur **Appareils IoT**. Ensuite, cliquez sur **+ Nouveau**.

	![Capture d’écran du volet des appareils IoT, mis en surbrillance dans le panneau de navigation du hub IoT, dans le portail Azure. Le bouton Nouveau est mis en surbrillance pour illustrer comment ajouter une nouvelle identité d’appareil IoT au hub IoT.](../images/0602.png)

3. Donnez un nom à votre nouvel appareil IoT, **myRaspberryPi**, puis cliquez sur le bouton **Enregistrer**. Cette opération crée une identité d’appareil IoT dans votre hub IoT Azure.

4. Si vous ne voyez pas votre nouvel appareil, **actualisez** la page Appareils IoT. 

5. Sélectionnez **myRaspberryPi** et copiez la valeur **Chaîne de connexion principale**. Vous utiliserez cette clé dans la tâche suivante pour authentifier une connexion auprès du simulateur Raspberry Pi.

	![Capture d’écran de la page Chaîne de connexion principale avec icône de copie en surbrillance.](../images/0603.png)

# Tâche 3 : Tester l’appareil à l’aide du simulateur Raspberry Pi

Dans cette tâche, nous allons tester notre appareil à l’aide du simulateur Raspberry Pi. 

1. Ouvrez un nouvel onglet dans le navigateur web et accédez au [simulateur Raspberry Pi en ligne](https://azure-samples.github.io/raspberry-pi-web-simulator/#Getstarted). 

2. Découvrez le simulateur Raspberry Pi. Si une fenêtre contextuelle d’aperçu s’affiche, cliquez sur "**X**" pour fermer la fenêtre.

3. Dans la zone de code, à droite, recherchez la ligne contenant 'const connectionString ='. Remplacez ce code par la chaîne de connexion que vous avez copiée à partir du portail Azure. Notez que la chaîne de connexion comprend les entrées DeviceId (**myRaspberryPi**) et SharedAccessKey.

	![Capture d’écran de la zone de codage dans le simulateur Raspberry Pi.](../images/0604.png)

4. Cliquez sur **Exécuter** (sous la zone de code) pour exécuter l’application. La sortie de la console doit afficher les données du capteur et les messages qui sont envoyés du simulateur Raspberry Pi à votre hub IoT Azure. Les données et les messages sont envoyés à chaque fois que la LED du simulateur Raspberry Pi clignote. 

	![Capture d’écran de la console du simulateur Raspberry Pi.  La sortie de la console affiche les données du capteur et les messages envoyés du simulateur Raspberry Pi au hub IoT Azure.](../images/0605.png)

5. Cliquez sur **Arrêter** pour interrompre l’envoi de données.

6. Retournez au portail Azure et à votre hub IoT.

7. Accédez au panneau **Vue d’ensemble** du hub IoT et faites défiler vers le bas jusqu’aux informations d’**utilisation du hub IoT**.

	![Capture d’écran des mesures dans la zone d’utilisation du hub IoT du portail Azure.](../images/0606.png)


Félicitations ! Vous avez configuré le hub IoT Azure pour collecter les données des capteurs à partir d’un appareil IoT.

**Remarque** : Pour éviter des coûts supplémentaires, vous pouvez supprimer ce groupe de ressources. Recherchez des groupes de ressources, cliquez sur votre groupe de ressources, puis sur **Supprimer le groupe de ressources**. Vérifiez le nom du groupe de ressources, puis cliquez sur **Supprimer**. Surveillez les **notifications** pour voir comment se déroule la suppression.
