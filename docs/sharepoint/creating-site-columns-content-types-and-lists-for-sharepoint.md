---
title: "Création de colonnes de Site, les Types de contenu et listes pour SharePoint | Documents Microsoft"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.ListDesigner.ContentTypeSetting
- VS.SharePointTools.ContentTypeDesigner.CommonPropertiesPage
- VS.SharePointTools.ListDesigner.CreatingLists
- VS.SharePointTools.ListDesigner.ListPage
- VS.SharePointTools.ListDesigner.ViewPage
- VS.SharePointTools.ListDesigner.CommonPropertiesPage
- VS.SharePointTools.ContentTypeDesigner.ColumnsPage
dev_langs:
- VB
- CSharp
ms.assetid: 9ceed263-3aec-41dc-8708-63cb37a08fa8
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a5f111efa5c2276adcc76fdf13cdf5a805929c63
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-site-columns-content-types-and-lists-for-sharepoint"></a>Création de colonnes de sites, de types de contenu et de listes pour SharePoint
  Visual Studio fournit des modèles d’élément de projet pour nombreux différents éléments fondamentaux de SharePoint, y compris *répertorie* et *types de contenu*, qui peuvent inclure des colonnes de site (ou  *champs*). Les nouveaux concepteurs de type de contenu et de listes facilitent plus que jamais la création de ces éléments.  
  
## <a name="site-columns"></a>Colonnes de site  
 Les colonnes de site font partie des éléments les plus critiques que vous puissiez ajouter à un projet SharePoint. Une colonne de site représente un type de données, tel qu'un numéro de téléphone, un commentaire, ou le nom d'une ville d'un contact dans une liste de contacts.  
  
 Le modèle de projet de site rend la création de colonnes de site plus facile que dans la version antérieure de Visual Studio. Après avoir créé une colonne de site, vous pouvez modifier le XML dans le fichier Elements.xml de la colonne de site pour inclure les informations souhaitées, telles que son nom complet, son type de données, et le groupe dans lequel vous voulez que la colonne de site s'affiche dans SharePoint. Pour plus d’informations sur les colonnes de site, consultez [Introduction aux colonnes](http://go.microsoft.com/fwlink/?LinkId=224996).  
  
## <a name="content-types-and-lists"></a>Types de contenu et listes  
 Les types de contenu et listes font partie des éléments les plus fréquemment utilisés dans SharePoint.  
  
 Un type de contenu définit les métadonnées, le flux de travail, et le comportement d'une catégorie d'éléments dans une liste ou une bibliothèque de documents SharePoint. Par exemple, vous pouvez créer un type de contenu pour les informations d'une liste de contacts ou de tâches. Un type de contenu de contact peut inclure des colonnes telles que le nom, l'adresse de courrier électronique, le numéro de téléphone, et l'adresse. Un type de contenu que vous définissez au niveau du site n'est associé à aucune liste ou bibliothèque de documents sur le site. Vous pouvez utiliser le même type de contenu avec des listes ou bibliothèques de documents sur le site SharePoint. Vous pouvez également utiliser plusieurs types de contenu sur la même liste ou bibliothèque de documents.  
  
 Une liste est une collection d'informations dans SharePoint que vous pouvez partager avec d'autres utilisateurs. Les listes sont constituées des lignes des colonnes qui contiennent des données. Des exemples de listes : une liste des tâches, une liste de contacts et une liste d'annonces.  
  
 Les nouveaux concepteurs des types de contenu et de liste dans [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] rendent la création des types et des listes beaucoup plus facile et intuitive que dans la version antérieure de Visual Studio. L'interface utilisateur vous permet de créer visuellement des types de contenu et des listes d'une façon qui vous est familière, et vous permet de trier et regrouper des données dans les listes et utiliser des en-têtes de groupe. Pour plus d’informations sur les types de contenu, consultez [des Types de contenu](http://go.microsoft.com/fwlink/?LinkId=224997). Pour plus d’informations sur les listes, consultez [liste Forms](http://go.microsoft.com/fwlink/?LinkId=224998) et [liste (vues)](http://go.microsoft.com/fwlink/?LinkId=224999).  
  
## <a name="related-topics"></a>Rubriques connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Procédure pas à pas : création d’une colonne de site, d’un type de contenu et d’une liste pour SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)|Illustre comment créer des colonnes de site utilisées dans un type de contenu personnalisé. Le type de contenu est ensuite utilisé dans une liste personnalisée.|  
  
## <a name="see-also"></a>Voir aussi  
 [Commencer à développer sur SharePoint 2010](http://go.microsoft.com/fwlink/?LinkId=225000)  
  
  