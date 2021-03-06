---
title: "Configuration d’un dépôt Subversion dans Visual Studio pour Mac | Microsoft Docs"
description: Utilisation de Git et de Subversion dans Visual Studio pour Mac.
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 0D58FB37-530E-495B-BED6-FD499477A9B6
ms.openlocfilehash: 0757ad29b8614a86f059f525f6ffe3100595d09b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="setting-up-a-subversion-repository"></a>Configuration d’un dépôt Subversion

Subversion est un système de gestion de versions centralisé. Cela signifie qu’il existe un seul serveur contenant tous les fichiers et révisions, à partir duquel les utilisateurs peuvent extraire n’importe quelle version de n’importe quel fichier. Quand les fichiers sont extraits d’un dépôt Subversion distant, l’utilisateur obtient une capture instantanée du dépôt à ce point dans le temps.

Avant de commencer à utiliser Subversion, les outils en ligne de commande Xcode doivent être installés, car ils incluent les packages SVN corrects. Vous pouvez vérifier que SVN est installé dans Terminal avec la commande suivante :

`svn h`

1. Créez un dépôt SVN gratuit en ligne. Pour cet exemple, [Assembla](https://app.assembla.com/) a été utilisé. Après la création, une URL est fournie, qui sera utilisée pour se connecter au dépôt : 

    ![Obtenir l’URL de SVN et la copier](media/version-control-subversion1-sml.png)

2. Ouvrez ou créez un projet Visual Studio pour Mac.

3. Cliquez avec le bouton droit sur le projet et sélectionnez **Gestion de version > Publier dans la gestion de version...** : 

    ![Démarrer la publication d’un projet](media/version-control-subversion2.png)

4. Dans l’onglet **Se connecter au dépôt**, sélectionnez **Subversion** dans la liste déroulante du haut.

5. Entrez l’URL de l’étape 1. Cette action doit normalement remplir les autres champs par défaut : 

    ![Boîte de dialogue Sélectionner un dépôt et entrer les détails](media/version-control-subversion3.png)

7. Cliquez sur **OK** puis confirmez en cliquant sur **Publier**.

7. Vous pouvez être invité à entrer vos informations d’identification pour le site sur lequel vous créez le dépôt. Entrez ces informations comme illustré ci-dessous :

    ![](media/version-control-subversion5.png)

8.  Toutes les commandes disponibles pour la gestion de versions doivent maintenant être visibles dans le menu Gestion de version.

