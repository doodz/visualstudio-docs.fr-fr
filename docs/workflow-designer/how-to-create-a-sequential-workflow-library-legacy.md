---
title: "Comment : créer une bibliothèque de flux de travail séquentiel (héritée) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- sequential workflows, creating library
- workflows, sequential workflow library
- projects, sequential workflow library
- sequential workflow libraries
ms.assetid: 9433ccf3-1eab-4d53-90ff-2e7b2341676c
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 52c78a49a468be929e93946b3b162c31370558dc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-create-a-sequential-workflow-library-legacy"></a>Procédure : créer une bibliothèque de workflows séquentiels (héritée)
Suivez ces étapes pour créer un projet de bibliothèque de workflows séquentiels à l'aide du [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] hérité fourni par [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]. Utilisez le [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] hérité lorsque vous devez cibler le [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] ou le [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
### <a name="to-create-a-sequential-workflow-library-project"></a>Pour créer un projet de bibliothèque de workflow séquentiel  
  
1.  Démarrez Visual Studio.  
  
2.  Sur le **fichier** menu, pointez sur **nouveau**, puis sélectionnez **projet**.  
  
     La boîte de dialogue **Nouveau projet** s'affiche.  
  
3.  Sélectionnez le **.NET Framework 3.0** option ou **.NET Framework 3.5** option dans la liste déroulante située en haut de la **nouveau projet** fenêtre pour accéder au concepteur hérité.  
  
    > [!NOTE]
    >  L’option par défaut dans [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] est **.NET Framework 4**. Cette option permet de créer des applications [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] qui ciblent le [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] et elle n'utilise pas le concepteur hérité.  
  
4.  Dans le **Types de projets** volet, sélectionnez Visual c# ou Visual Basic (sous **autres langages**), puis sélectionnez **Workflow**.  
  
5.  Dans le **modèles** volet, sélectionnez **bibliothèque de flux de travail séquentiel**.  
  
6.  Dans le **nom** , entrez un nom descriptif pour votre projet afin de faciliter son identification.  
  
7.  Dans le **emplacement** , entrez le répertoire dans lequel vous souhaitez enregistrer votre projet, ou cliquez sur la zone **Parcourir** pour naviguer jusqu'à lui.  
  
     Si vous souhaitez un répertoire de solution créé pour le projet, sélectionnez le **créer le répertoire pour la solution** case à cocher et entrez un nom dans la **nom de la Solution** boîte.  
  
8.  Cliquez sur **OK**.  
  
## <a name="see-also"></a>Voir aussi  
 [Création de projets de Workflow hérité](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Styles de création de flux de travail](http://msdn.microsoft.com/en-us/aacf4ec6-da05-4974-958a-974769dda739)