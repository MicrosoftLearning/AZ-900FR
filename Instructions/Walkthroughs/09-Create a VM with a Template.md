---
wts:
    title: '09 - Créer une machine virtuelle avec un modèle (10 minutes)'
    module: 'Module 03 : Décrire les solutions principales et les outils de gestion'
---
# 09 - Créer une machine virtuelle avec un modèle

Dans cette procédure pas à pas, nous allons déployer une machine virtuelle avec un modèle de démarrage rapide et examiner ses capacités de surveillance.

# Tâche 1 : Parcourir la galerie et trouver un modèle (10 minutes)

Dans cette tâche, nous allons parcourir la galerie de démarrage rapide Azure et déployer un modèle qui crée une machine virtuelle. 

1. Dans un navigateur, accédez à la [Galerie de modèles de démarrage rapide Azure](https://azure.microsoft.com/resources/templates?azure-portal=true). Dans la galerie, vous trouverez un certain nombre de modèles courants et récemment mis à jour. Ces modèles automatisent le déploiement des ressources Azure, y compris l’installation de packages logiciels courants.

2. Parcourez les différents types de modèles disponibles. 

    **Remarque** : Y a-t-il des modèles qui vous intéressent ?

3. Recherchez le modèle [Déployer une machine virtuelle](https://azure.microsoft.com/resources/templates/101-vm-simple-windows?azure-portal=true) ou accédez-y directement.

    **Remarque** : Le bouton **Déployer sur Azure** vous permet de déployer le modèle via le portail Azure. Lors d’un tel déploiement, vous serez invité uniquement à définir un ensemble limité de paramètres de configuration. 

4. Cliquez sur le bouton **Déployer sur Azure**. Votre session de navigateur sera automatiquement redirigée vers le [portail Azure](http://portal.azure.com/).

5. Si vous y êtes invité, connectez-vous à l’abonnement Azure que vous souhaitez utiliser dans ce labo.

6. Cliquez sur **Modifier le modèle**. Le format de modèle Resource Manager utilise le format JSON. Vérifiez les paramètres et les variables.  Localisez ensuite le paramètre du nom de la machine virtuelle. Remplacez le nom par **myVMTemplate**. **Enregistrez** vos modifications. Vous êtes redirigé vers le panneau **Déploiement personnalisé** dans le portail Azure.

    ![Capture d’écran du modèle avec le changement de nom de la machine virtuelle en surbrillance.](../images/0901.png)

7. Sur le panneau **Déploiement personnalisé**, configurez les paramètres requis par le modèle (remplacez ***xxxx*** dans le préfixe d’étiquette DNS par des lettres et des chiffres, de sorte que l’étiquette soit unique au monde). Laissez les valeurs par défaut pour tous les autres éléments. 

    | Paramètre| Valeur|
    |----|----|
    | Abonnement | **Choisissez votre abonnement**|
    | Groupe de ressources | **myRGTemplate** (créer un nouveau) |
    | Localisation | **(États-Unis) USA Est** |
    | Nom d’utilisateur administrateur | **azureuser** |
    | Mot de passe administrateur | **Pa$$w0rd1234** |
    | Préfixe d’étiquette DNS | **myvmtemplate*xxxx*** |
    | Version du système d’exploitation Windows | **2019-Datacenter** |
    | | |
    
    **Remarque** : Il n’y a pas de coûts associés à l’utilisation de ce modèle.

8. Cliquez sur **Examiner et créer**.

9. Une fois la validation réussie, cliquez sur le bouton **Créer**. Le déploiement de la machine virtuelle peut prendre de cinq à sept minutes. 

# Tâche 2 : Vérifier et contrôler le déploiement de votre machine virtuelle

Dans cette tâche, nous allons vérifier si la machine virtuelle s’est correctement déployée. 

1. Dans le panneau **Tous les services**, recherchez et sélectionnez **Machines virtuelles**.

2. Assurez-vous que votre nouvelle machine virtuelle a été créée. 

    ![Capture d’écran de la page des machines virtuelles. La nouvelle machine virtuelle est affichée et fonctionne.](../images/0902.png)

3. Sélectionnez votre machine virtuelle puis, dans le volet **Vue d’ensemble**, faites défiler vers le bas pour afficher les données de surveillance.

    **Remarque** : Le délai de surveillance peut être ajusté, de une heure à 30 jours.

4. Passez en revue les différents graphiques fournis, y compris **UC (moyenne)**, **Réseau (total)**, et **Octets de disque (total)**. 

    ![Capture d’écran des graphiques de surveillance des machines virtuelles.](../images/0903.png)

5. Cliquez sur un graphique. Remarquez que vous pouvez **Ajouter une mesure** et modifier le type de graphique.

6. Revenez au panneau **Vue d’ensemble**.

7. Cliquez sur le **journal d’activité** (volet gauche). Les journaux d’activité enregistrent des événements tels que la création ou la modification de ressources. 

8. Cliquez sur **Ajouter un filtre** et recherchez différents types d’événements et d’opérations afin de vous familiariser avec cette option. 

    ![Capture d’écran de la page Ajouter des filtres avec le type d’événement sélectionné.](../images/0904.png)

**Remarque** : Pour éviter des coûts supplémentaires, vous pouvez supprimer ce groupe de ressources. Recherchez des groupes de ressources, cliquez sur votre groupe de ressources, puis sur **Supprimer le groupe de ressources**. Vérifiez le nom du groupe de ressources, puis cliquez sur **Supprimer**. Surveillez les **notifications** pour voir comment se déroule la suppression.
