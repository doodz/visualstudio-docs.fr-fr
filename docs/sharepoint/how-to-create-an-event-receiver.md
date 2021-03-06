---
title: "Comment : créer un récepteur d’événements | Documents Microsoft"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.SPE.EventReceiver
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
ms.assetid: 6f90cb48-eb8f-43c2-a3f7-ed4ce81aedf2
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 938c03a0bea5a4e96885f1816ddb1c1c13d80ce0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-an-event-receiver"></a>Comment : créer un récepteur d'événements
  En créant *récepteurs d’événements*, vous pouvez répondre lorsqu’un utilisateur interagit avec les éléments SharePoint telles que les listes ou des éléments de liste. Par exemple, le code dans un récepteur d’événements peut être déclenché lorsqu’un utilisateur modifie le calendrier ou supprime un nom à partir d’une liste de contacts. En suivant cette rubrique, vous pouvez apprendre à ajouter un récepteur d’événements à une instance de liste.  
  
 Pour effectuer ces étapes, vous devez avoir installé [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] et éditions de Windows et de SharePoint prises en charge. Pour plus d’informations, consultez [configuration requise pour le développement de Solutions SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md). Étant donné que cet exemple requiert un projet SharePoint, vous également devez avoir terminé la procédure décrite dans la rubrique [procédure pas à pas : création d’une colonne de Site, le Type de contenu et la liste pour SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).  
  
## <a name="adding-an-event-receiver"></a>Ajout d’un récepteur d’événements  
 Le projet que vous avez créé dans [procédure pas à pas : création d’une colonne de Site, le Type de contenu et la liste pour SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) inclut des colonnes de site personnalisées, une liste personnalisée et un type de contenu. Dans la procédure suivante, vous allez développer ce projet en ajoutant un gestionnaire d’événements simple (un récepteur d’événements) à une instance de liste pour montrer comment gérer les événements qui se produisent dans les éléments tels que des listes SharePoint.  
  
#### <a name="to-add-an-event-receiver-to-the-list-instance"></a>Pour ajouter un récepteur d’événements pour l’instance de liste  
  
1.  Ouvrez le projet que vous avez créé dans [procédure pas à pas : création d’une colonne de Site, le Type de contenu et la liste pour SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).  
  
2.  Dans **l’Explorateur de solutions**, choisissez le nœud de projet SharePoint, qui est nommé **Clinic**.  
  
3.  Dans la barre de menus, choisissez **projet**, **ajouter un nouvel élément**.  
  
4.  Sous **Visual C#** ou **Visual Basic**, développez le **SharePoint** nœud, puis choisissez le **2010** élément.  
  
5.  Dans le **modèles** volet, choisissez **récepteur d’événements**, nommez-le **TestEventReceiver1**, puis choisissez le **OK** bouton.  
  
     Le **Assistant Personnalisation de SharePoint** s’affiche.  
  
6.  Dans le **le type de récepteur d’événements voulez-vous ?** , choisissez **événements d’élément de liste**.  
  
7.  Dans le **quel élément doit être la source d’événements ?** , choisissez **Patients (Clinic\Patients)**.  
  
8.  Dans le **gérer les événements suivants** , sélectionnez la case à cocher à côté **un élément a été ajouté**, puis choisissez le **Terminer** bouton.  
  
     Le fichier de code pour le récepteur d’événements contient une méthode unique nommée `ItemAdded`. Dans l’étape suivante, vous ajouterez du code à cette méthode afin que chaque contact nommée Scott Brown par défaut.  
  
9. Remplacer la `ItemAdded` méthode avec les éléments suivants de code, puis choisissez la touche F5 :  
  
     [!code-csharp[SP_EventReceiver#1](../sharepoint/codesnippet/CSharp/CustomField1/TestEventReceiver1/TestEventReceiver1.cs#1)]
     [!code-vb[SP_EventReceiver#1](../sharepoint/codesnippet/VisualBasic/CustomField1_VB/EventReceiver1/EventReceiver1.vb#1)]  
  
     Le code est exécuté et le site s’affiche dans le navigateur web de SharePoint.  
  
10. Dans la barre de lancement rapide, choisissez le **Patients** lier, puis choisissez le **ajouter un nouvel élément** lien.  
  
     Le formulaire d’entrée pour les nouveaux éléments s’ouvre.  
  
11. Entrez des données dans les champs, puis choisissez le **enregistrer** bouton.  
  
     Après avoir choisi le **enregistrer** bouton, le **nom du Patient** colonne met automatiquement à jour le nom Scott Brown.  
  
## <a name="see-also"></a>Voir aussi  
 [Développement de solutions SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  