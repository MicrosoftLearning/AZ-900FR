---
wts:
    title: '12 - Implémenter Azure Key Vault (5 minutes)'
    module: 'Module 04 : Description des fonctionnalités de sécurité générale et de sécurité réseau'
---
# 12 - Implémenter Azure Key Vault

Dans cette procédure pas à pas, nous allons créer un coffre de clés Azure (Key vault), puis créer un mot de passe secret dans ce coffre de clés, fournissant un mot de passe stocké en toute sécurité et géré de manière centralisée en vue d’une utilisation dans les applications.

# Tâche 1 : Créer une instance Azure Key Vault (5 minutes)

1. Connectez-vous au [portail Azure](https://portal.azure.com).

2. Dans le panneau **Tous les services**, recherchez et sélectionnez **Coffres de clés**, puis sélectionnez **+ Ajouter, + Créer ou + Nouveau**.

3. Configurer le coffre de clés (remplacer **xxxx** dans le nom du coffre de clés par des lettres et des chiffres pour que le nom soit unique au monde). Laissez les valeurs par défaut pour tous les autres éléments.

    | Paramètre | Valeur | 
    | --- | --- |
    | Abonnement | **Utilisez votre abonnement** |
    | Groupe de ressources | **myRGKV** (créer un nouveau) |
    | Nom du coffre de clés | **keyvaulttestxxx** |
    | Localisation | **USA Est** |
    | Niveau tarifaire | **Standard** |
    | | |

4. Cliquez sur **Examiner et créer** puis, après la validation, cliquez sur **Créer**. 

5. Une fois le nouveau coffre de clés configuré, cliquez sur **Accéder à la ressource**. Vous pouvez également localiser votre nouveau coffre de clés en le recherchant. 

6. Cliquez sur l’onglet **Aperçu** dans Key Vault et prenez note du **nom DNS**. Les applications qui utilisent votre coffre via l’API REST auront besoin de cet URI.

7. Prenez un moment pour parcourir certaines des autres options du coffre de clés. Sous **Paramètres**, vérifiez **Clés**, **Secrets**, **Certificats**, **Stratégies d’accès**, **Pare-feu et réseaux virtuels**.

    **Remarque** : Votre compte Azure est le seul autorisé à effectuer des opérations sur ce nouveau coffre. Vous pouvez le modifier si vous le souhaitez dans les **Paramètres** puis dans la section **Stratégies d’accès**.

# Tâche 2 : Ajouter un secret au coffre de clés
        
Dans cette tâche, nous ajouterons un mot de passe au coffre à clés. 

1. Sous **Paramètres**, cliquez sur **Secrets**, puis sur **+ Générer/Importer**.

2. Configurez le secret. Conservez les valeurs par défaut pour tous les autres éléments. Notez que vous pouvez définir une date d’activation et une date d’expiration. Notez que vous pouvez également désactiver le secret.

    | Paramètre | Valeur | 
    | --- | --- |
    | Options de chargement | **Manuel** |
    | Nom | **ExamplePassword** |
    | Valeur | **hVFkk96** |
    | | |

3. Cliquez sur **Créer**.

4. Une fois le secret créé, cliquez sur **ExamplePassword** et notez qu’il a le statut **Activé**

5. Cliquez sur la version actuelle, notez l’**Identificateur de secret**. Il s’agit de la valeur de l’URL que vous pouvez désormais utiliser avec les applications. Il fournit un mot de passe géré de manière centralisée et stocké en toute sécurité.

6. Cliquez sur le bouton **Afficher la valeur du secret** pour afficher le mot de passe que vous avez spécifié précédemment.

Félicitations ! Vous avez créé un coffre de clés Azure, puis créé un mot de passe secret dans ce coffre de clés. Vous disposez donc d’un mot de passe sécurisé et géré de manière centralisée, qui peut être utilisé dans les applications.

**Remarque** : Pour éviter des coûts supplémentaires, vous pouvez supprimer ce groupe de ressources. Recherchez des groupes de ressources, cliquez sur votre groupe de ressources, puis sur **Supprimer le groupe de ressources**. Vérifiez le nom du groupe de ressources, puis cliquez sur **Supprimer**. Surveillez les **notifications** pour voir comment se déroule la suppression.
