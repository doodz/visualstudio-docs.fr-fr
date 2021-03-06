---
title: "Étendre des éléments de projet SharePoint | Documents Microsoft"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
ms.assetid: f09f6664-196d-46d6-819f-3c6500f23536
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8f17e43e2fe98e36939c91b37e72b185cb14d09e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-sharepoint-project-items"></a>Extension d'éléments de projet SharePoint
  Créer une extension d’élément de projet lorsque vous souhaitez ajouter des fonctionnalités à un type d’élément de projet SharePoint est déjà installé dans Visual Studio. Par exemple, vous pouvez créer une extension pour la fonction intégrée **récepteur d’événements** ou **définition de liste** les éléments de projet dans Visual Studio, ou vous pouvez créer une extension pour un type d’élément de projet personnalisé. Vous pouvez également créer une extension pour tous les types d’éléments de projet SharePoint.  
  
## <a name="tasks-for-extending-sharepoint-project-items"></a>Tâches pour l’extension d’éléments de projet SharePoint  
 Pour étendre un élément de projet, créez un assembly d’extension Visual Studio qui implémente le <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> interface. Pour plus d’informations, consultez [Comment : créer une Extension d’élément de projet SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
 Lorsque vous étendez un élément de projet, vous pouvez également ajouter les fonctionnalités suivantes à l’élément de projet :  
  
-   Ajouter un élément de menu contextuel pour l’élément de projet. L’élément de menu s’affiche lorsque vous ouvrez le menu contextuel pour l’élément de projet dans **l’Explorateur de solutions**. Vous ouvrez le menu contextuel en cliquant sur l’élément de projet ou en le sélectionnant et en appuyant sur la touche MAJ + F10 clés. Pour plus d’informations, consultez [Comment : ajouter un élément de Menu contextuel à une Extension d’élément de projet SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md).  
  
-   Ajouter une propriété personnalisée à l’élément de projet. La propriété apparaît dans le **propriétés** fenêtre lorsque vous choisissez l’élément de projet dans **l’Explorateur de solutions**. Pour plus d’informations, consultez [Comment : ajouter une propriété à une Extension d’élément de projet SharePoint](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md).  
  
 Pour une procédure pas à pas qui montre comment créer, déployer et tester une extension d’élément de projet, consultez [procédure pas à pas : étendre un Type d’élément de projet SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md).  
  
## <a name="understanding-the-relationship-between-project-item-extensions-and-project-item-instances"></a>Présentation de la relation entre les Extensions d’élément de projet et les Instances d’élément de projet  
 Lorsque vous créez une extension d’élément de projet, Visual Studio charge votre extension lorsqu’un élément de projet du type associé est ajouté à un projet SharePoint. Par exemple, si vous créez une extension pour **récepteur d’événements** des éléments de projet, Visual Studio charge votre extension lorsqu’un utilisateur ajoute un **récepteur d’événements** élément de projet pour un projet. Visual Studio utilise la même instance de votre extension pour toutes les instances du type d’élément de projet associé. Dans l’exemple précédent, si l’utilisateur ajoute un deuxième **récepteur d’événements** d’éléments de projet au projet, la même instance de votre extension est utilisée pour personnaliser le deuxième élément de projet.  
  
 Pour accéder à une instance spécifique du type d’élément de projet vous étendez, gérez l’un de la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> les événements de la *projectItemType* paramètre dans votre implémentation de la <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> (méthode). Par exemple, pour déterminer quand un élément de projet du type que vous étendez est ajouté à un projet, gérer les <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> événement. Pour plus d’informations, consultez [Comment : créer une Extension d’élément de projet SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
## <a name="identifiers-for-sharepoint-project-items"></a>Identificateurs pour les éléments de projet SharePoint  
 Chaque élément de projet SharePoint a un identificateur de chaîne correspondante. Vous devez connaître l’identificateur pour un élément de projet si vous souhaitez effectuer les tâches suivantes :  
  
-   Créer une extension pour l’élément de projet. Dans ce cas, vous devez passer l’identificateur de l’élément de projet que vous souhaitez étendre au constructeur de la <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Pour créer une extension pour tous les types de projet élément, transmettez la  **\***  valeur de chaîne.  
  
-   Ajouter l’élément de projet à un projet par programmation. Dans ce cas, vous devez passer l’identificateur de l’élément de projet pour le <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemCollection.Add%2A> (méthode).  
  
 Le tableau suivant répertorie les identificateurs pour les éléments de projet SharePoint qui sont inclus dans Visual Studio.  
  
|Nom d’élément de projet|Identificateur de chaîne|  
|-----------------------|-----------------------|  
|Modèle de catalogue de données métiers|Microsoft.VisualStudio.SharePoint.BusinessDataConnectivity|  
|Type de contenu|Microsoft.VisualStudio.SharePoint.ContentType|  
|Récepteur d’événements|Microsoft.VisualStudio.SharePoint.EventHandler|  
|Élément vide|Microsoft.VisualStudio.SharePoint.GenericElement|  
|Définition de liste<br /><br /> Définition de liste à partir du Type de contenu|Microsoft.VisualStudio.SharePoint.ListDefinition|  
|Instance de liste|Microsoft.VisualStudio.SharePoint.ListInstance|  
|Module|Microsoft.VisualStudio.SharePoint.Module|  
|Flux de travail séquentiel<br /><br /> Flux de travail de l'ordinateur d'état|Microsoft.VisualStudio.SharePoint.Workflow|  
|Définition de site|Microsoft.VisualStudio.SharePoint.SiteDefinition|  
|Composant Visual Web Part|Microsoft.VisualStudio.SharePoint.VisualWebPart|  
|Composant Web Part|Microsoft.VisualStudio.SharePoint.WebPart|  
|Formulaire d’Association de flux de travail|Microsoft.VisualStudio.SharePoint.WorkflowAssociation|  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : créer une Extension d’élément de projet SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [Comment : ajouter un élément de Menu contextuel à une Extension d’élément de projet SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)   
 [Comment : ajouter une propriété à une Extension d’élément de projet SharePoint](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)   
 [Procédure pas à pas : Étendre un Type d’élément de projet SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)   
 [Extension du système de projet SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)  
  