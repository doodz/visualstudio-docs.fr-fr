---
title: "Comment : synchroniser des ensembles de règles de projet de Code avec la stratégie d’archivage du projet d’équipe | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.selecttfsruleset
ms.assetid: 9b02f934-2db6-41ec-aaff-9c31ceec2f04
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: de3a7bfaccec45dc6b7fce1def45a6e6de8e75f2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy"></a>Comment : synchroniser des ensembles de règles applicables à des projets de code avec la stratégie d'archivage du projet d'équipe
Vous synchronisez les paramètres d’analyse de code pour les projets de code à la stratégie d’archivage du projet d’équipe en spécifiant un ensemble de règles qui contient au moins les règles spécifiées dans l’ensemble de règles pour la stratégie d’archivage. Votre responsable du développement peut informer vous du nom et l’emplacement de l’ensemble de règles pour la stratégie d’archivage. Vous pouvez utiliser une des options suivantes pour vous assurer que l’analyse du code pour le projet utilise le jeu de règles approprié :  
  
-   Si la stratégie d’archivage utilise un des ensembles de règles intégrés Microsoft, ouvrez la boîte de dialogue Propriétés du projet de code, afficher la page d’analyse du Code et sélectionnez la règle définie sur la page d’analyse du Code des paramètres de projet de code. L’ensembles de règles standard sont installés automatiquement avec Visual Studio de Microsoft sont la valeur en lecture seule et ne doit pas être modifié. Si les ensembles de règles ne sont pas modifiés, les règles de la stratégie et les ensembles de règles locales sont garantis pour correspondre.  
  
-   Si la stratégie d’archivage utilise un ensemble de règles personnalisé, effectuer une opération get sur le fichier d’ensemble de règles de contrôle de version pour créer une copie locale. Spécifiez ensuite cet emplacement local dans les paramètres d’analyse de code pour le projet de code. Les règles sont garanties à faire correspondre si l’ensemble de règles pour la stratégie d’archivage est à jour.  
  
     Si vous mappez l’emplacement de contrôle de version à un dossier local qui se trouve dans la même relation à la racine du projet d’équipe en tant que votre projet de code, l’emplacement de la règle est défini à l’aide d’un chemin d’accès relatif. Le chemin d’accès relatif garantit que le paramètre de projet pour l’analyse du code peut être déplacé vers d’autres ordinateurs.  
  
-   Personnaliser une copie de l’ensemble de règles pour la stratégie d’archivage pour un projet de code. Assurez-vous que le nouvel ensemble de règles contient toutes les règles dans la stratégie d’archivage et les autres règles que vous souhaitez inclure. Il se peut que vous devez vous assurer que votre jeu de règles inclut toutes les règles dans l’ensemble de règles pour la stratégie d’archivage.  
  
### <a name="to-specify-a-microsoft-standard-rule-set"></a>Pour spécifier une règle standard Microsoft ensemble  
  
1.  Dans **l’Explorateur de solutions**, cliquez sur le projet de code, puis cliquez sur **propriétés**.  
  
2.  Cliquez sur **l’analyse du Code**.  
  
3.  Dans le **exécuter cet ensemble de règles** , cliquez sur l’ensemble de règles de stratégie d’archivage.  
  
### <a name="to-specify-a-custom-check-in-policy-rule-set"></a>Pour spécifier un ensemble de règles de stratégie d’archivage personnalisée  
  
1.  Si nécessaire, effectuer une opération get sur le fichier d’ensemble de règles qui spécifie la stratégie d’archivage.  
  
2.  Dans **l’Explorateur de solutions**, cliquez sur le projet de code, puis cliquez sur **propriétés**.  
  
3.  Cliquez sur **l’analyse du Code**.  
  
4.  Dans le **exécuter cet ensemble de règles** , cliquez sur  **\<Parcourir... >**.  
  
5.  Dans le **ouvrir** boîte de dialogue, spécifiez le fichier d’ensemble de la règle de stratégie d’archivage.  
  
### <a name="to-create-a-custom-rule-set-for-a-code-project"></a>Pour créer une règle personnalisée définie pour un projet de code  
  
1.  Suivez une des procédures plus haut dans cette rubrique pour sélectionner la stratégie d’archivage du projet d’équipe dans la page de l’analyse du Code de la boîte de dialogue Paramètres du projet.  
  
2.  Cliquez sur **ouvrir**.  
  
3.  Ajouter ou supprimer des règles à l’aide de l’éditeur d’ensemble de règles.  
  
     Pour plus d’informations, consultez [création d’ensembles de règles personnalisés](../code-quality/creating-custom-code-analysis-rule-sets.md).  
  
4.  Enregistrer la règle modifiée définie dans un fichier .ruleset sur l’ordinateur local ou sur un chemin d’accès UNC.  
  
5.  Ouvrir la boîte de dialogue Propriétés du projet de code et afficher le **l’analyse du Code** page.  
  
6.  Dans le **exécuter cet ensemble de règles** , cliquez sur  **\<Parcourir... >**.  
  
7.  Dans le **ouvrir** boîte de dialogue, spécifiez le fichier d’ensemble de la règle.