---
title: "Comment : ajouter et supprimer des fonctionnalités et des éléments dans un Package à l’aide de l’Explorateur de package | Documents Microsoft"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.RAD.PackagingExplorer
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, packages
ms.assetid: 549d5848-f0c9-42c6-b7f5-bc1e626a30e6
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bafa2a4310a77f9f5a9f061e378ac05f2896d4ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer"></a>Comment : ajouter et supprimer des fonctionnalités et des éléments dans un package à l’aide de l’Explorateur de package
  Pour configurer un package pour déployer des éléments de SharePoint et les fonctionnalités, vous pouvez utiliser l’Explorateur de package. Vous pouvez ajuster les éléments de projet SharePoint et les fonctionnalités à l’intérieur de votre fichier .wsp.  
  
 Ou bien, vous pouvez utiliser le Concepteur d’empaquetage pour afficher et réorganiser les fonctionnalités pour modifier l’ordre d’activation. Pour plus d’informations, consultez [Comment : ajouter et supprimer des fonctionnalités et des éléments dans un Package à l’aide du Concepteur de packages](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md).  
  
## <a name="opening-the-packaging-explorer"></a>Ouverture de l’Explorateur de package  
 Vous pouvez utiliser la procédure suivante pour ouvrir l’Explorateur de package, si votre solution Visual Studio possède au moins un projet SharePoint. Vous pouvez également, l’Explorateur de package s’ouvre automatiquement lorsque vous affichez un concepteur de fonctionnalités ou de packages. Après avoir fermé tous les concepteurs de fonctionnalité et de package, l’Explorateur de package se ferme également.  
  
#### <a name="to-open-the-packaging-explorer"></a>Pour ouvrir l’Explorateur de package  
  
1.  Dans la barre de menus, choisissez **vue**, **autres fenêtres**, **Explorateur de package**.  
  
     Le **Explorateur de package** s’affiche dans le **boîte à outils**.  
  
## <a name="adding-a-feature-to-a-package"></a>Ajout d’une fonctionnalité à un Package  
 Vous pouvez ajouter des fonctionnalités nouvelles et existantes à un Package à l’aide de l’Explorateur de package.  
  
#### <a name="to-add-a-sharepoint-feature"></a>Pour ajouter une fonctionnalité SharePoint  
  
1.  Ouvrez le **Explorateur de package**, ouvrez le menu contextuel du projet, puis choisissez **ajouter une fonctionnalité**.  
  
#### <a name="to-move-an-existing-sharepoint-feature"></a>Pour déplacer une fonctionnalité SharePoint existante  
  
1.  Ouvrez le **Explorateur de package**, puis effectuez une des opérations suivantes :  
  
    -   Faites glisser un **fonctionnalité** d’un projet vers un autre projet.  
  
    -   Ouvrez le menu contextuel pour une fonctionnalité, choisissez **couper**, ouvrez le menu contextuel pour le projet auquel vous souhaitez déplacer la fonctionnalité, puis choisissez **coller**.  
  
    > [!NOTE]  
    >  Utilisez cette procédure si vous avez plusieurs projets SharePoint dans votre solution.  
  
## <a name="validating-a-feature-or-package"></a>Valider une fonctionnalité ou un Package  
 Vous pouvez identifier les problèmes potentiels dans les fonctionnalités de SharePoint et les packages en validant les fichiers. Erreurs et des avertissements sont affichent dans la fenêtre Sortie et la fenêtre liste d’erreurs.  
  
#### <a name="to-validate-a-sharepoint-feature-or-package"></a>Pour valider une fonctionnalité SharePoint ou un package  
  
1.  Ouvrez le **Explorateur de package**.  
  
2.  Ouvrir un menu contextuel pour une fonctionnalité ou un package, puis choisissez **Validate**.  
  
## <a name="see-also"></a>Voir aussi  
 [Empaquetage et déploiement de solutions SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  