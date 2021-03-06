---
title: Solutions Visio | Documents Microsoft
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
- Office projects [Office development in Visual Studio], Visio
- solutions [Office development in Visual Studio], Visio
- Visio [Office development in Visual Studio]
- templates [Office development in Visual Studio], Visio
- projects [Office development in Visual Studio], Visio
- Office solutions [Office development in Visual Studio], Visio
ms.assetid: c52948c6-6891-43ec-93ff-c54c74ec6016
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b09e0a43f4a9dbb77a983a1f7e87f0b2886b1697
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="visio-solutions"></a>Solutions Visio
  Visual Studio fournit des modèles de projet que vous pouvez utiliser pour créer des compléments VSTO pour Microsoft Office Visio. Vous pouvez utiliser les compléments VSTO pour automatiser Visio, étendre les fonctionnalités Visio ou personnaliser l'interface utilisateur de Visio.  
  
 Pour plus d’informations sur les compléments VSTO, consultez [Getting Started Programming VSTO Add-ins](../vsto/getting-started-programming-vsto-add-ins.md) et [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md). Si vous débutez en programmation avec Microsoft Office, consultez [mise en route &#40; développement Office dans Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 **S’applique à :** les informations contenues dans cette rubrique s’appliquent aux projets de compléments VSTO pour Visio 2010. Pour plus d'informations, consultez [Features Available by Office Application and Project Type](../vsto/features-available-by-office-application-and-project-type.md).  
  
> [!NOTE]  
>  Vous souhaitez développer des solutions qui étendent l’expérience Office sur [plusieurs plateformes](https://dev.office.com/add-in-availability)? Découvrez le nouvel [modèle des compléments Office](https://dev.office.com/docs/add-ins/overview/office-add-ins). Compléments Office ont un faible encombrement mémoire par rapport aux compléments VSTO et les solutions, et vous pouvez les créer à l’aide de presque n’importe quel web technologies, telles que HTML5, JavaScript, CSS3 et XML de programmation.  
  
## <a name="automating-visio-by-using-the-visio-object-model"></a>Automatisation de Visio à l'aide du modèle objet Visio  
 Le modèle objet Visio expose de nombreuses classes que vous pouvez utiliser pour automatiser Visio afin de créer des diagrammes pour les organigrammes, diagrammes de flux, chronologies de projet, réseaux de tâches, espaces de bureau, etc. L'API vous permet d'écrire du code pour accomplir les tâches courantes :  
  
-   Élaborer et positionner des formes et du texte dans les diagrammes.  
  
-   Gérer le comportement des formes en fonction de la logique métier et des entrées d'utilisateur.  
  
-   Contrôler la visualisation des diagrammes, comme l'affichage panoramique et le zoom.  
  
-   Personnaliser l'interface utilisateur de l'application.  
  
-   Importer des données externes dans Visio, les lier aux formes et les afficher graphiquement dans une page.  
  
 Vous pouvez visualiser des procédures pas à pas et des exemples de code illustrant l’utilisation du modèle objet de Visio pour utiliser des documents et des formes dans [Working with Visio Documents](../vsto/working-with-visio-documents.md) et [Working with Visio Shapes](../vsto/working-with-visio-shapes.md).  
  
 Pour accéder au modèle objet Visio à partir d'un complément VSTO, utilisez le champ `Application` de la classe `ThisAddIn` dans votre projet. Le `Application` champ retourne un objet Microsoft.Office.Interop.Visio.Application qui représente l’instance actuelle de Visio. Pour plus d'informations, consultez [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md).  
  
 Quand vous appelez le modèle objet Visio, vous utilisez des types fournis dans l'assembly PIA (Primary Interop Assembly) pour Visio. L'assembly PIA fait office de pont entre le code managé du complément VSTO et le modèle objet COM dans Visio. Tous les types dans l’assembly PIA de Visio sont définis dans l’espace de noms Microsoft.Office.Interop.Visio. Pour plus d’informations sur les assemblys PIA, consultez [présentation du développement de Solutions Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) et [assemblys PIA Office](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="visio-object-model-overview"></a>Vue d'ensemble du modèle objet Visio  
 Vous trouverez une vue d’ensemble du modèle objet Visio dans [Visio Object Model Overview](../vsto/visio-object-model-overview.md), qui inclut des liens vers la référence du modèle objet Visio et les Kits de développement logiciel (SDK).  
  
## <a name="customizing-the-user-interface-of-visio"></a>Personnalisation de l'interface utilisateur de Visio  
 L'interface utilisateur de Visio inclut les options de personnalisation suivantes.  
  
|Tâche|Pour plus d'informations|  
|----------|--------------------------|  
|Personnaliser le ruban|[Vue d’ensemble du ruban](../vsto/ribbon-overview.md)|  
  
 Pour plus d'informations sur la personnalisation de l'interface utilisateur de Visio, consultez la documentation de référence sur VBA pour la classe [Visio.UIObject](https://msdn.microsoft.com/library/office/ff765763.aspx) .  
  
## <a name="see-also"></a>Voir aussi  
 [Getting Started Programming VSTO Add-ins](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Présentation du développement de Solutions Office &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Architecture des Compléments VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Comment : créer des projets Office dans Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [Écriture de Code dans les Solutions Office](../vsto/writing-code-in-office-solutions.md)   
 [Assemblys PIA Office](../vsto/office-primary-interop-assemblies.md)   
 [Personnalisation de l’interface utilisateur Office](../vsto/office-ui-customization.md)   
 [Vue d’ensemble du modèle objet Visio](../vsto/visio-object-model-overview.md)   
 [Développement Office Visio 2010](http://go.microsoft.com/fwlink/?LinkId=199017)  
  
  