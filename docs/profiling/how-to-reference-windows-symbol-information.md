---
title: "Guide pratique pour référencer les informations de symboles Windows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, symbol servers
- servers, symbol servers
- profiling tools, symbol servers
- symbol servers
ms.assetid: b7c67318-6be2-4b1e-a161-077b1f4a7c30
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09e17cc1e28ad520f76d60c3411de4803a2b4b96
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-reference-windows-symbol-information"></a>Guide pratique pour référencer les informations de symboles Windows
Les outils de profilage Visual Studio utilisent des fichiers de symboles (.pdb) pour résoudre les noms symboliques, tels que les noms de fonctions dans les fichiers binaires d’un programme. Vous pouvez suivre les étapes suivantes pour télécharger et mettre à jour automatiquement les fichiers .pdb correspondant à la version de Windows installée sur l’ordinateur local.  
  
> [!NOTE]
>  Ce paramètre n’affecte pas les rapports existants. Seuls ceux créés après la spécification du serveur de symboles auront les informations de symboles.  
  
 Pour plus d’informations, consultez [Spécifier les fichiers de symboles (.pdb) et les fichiers sources](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
### <a name="to-use-the-microsoft-symbol-server"></a>Pour utiliser le serveur de symboles Microsoft  
  
1.  Créez un dossier destiné à contenir les informations du fichier de symboles (par exemple, C:\SymbolCache).  
  
2.  Dans le menu **Outils** , cliquez sur **Options**.  
  
     La boîte de dialogue **Options** s'affiche.  
  
3.  Développez l’arborescence **Débogage**, puis cliquez sur **Symboles**.  
  
4.  Dans **Emplacements du fichier de symboles (.pdb)**, sélectionnez **Serveurs de symboles Microsoft**.  
  
5.  Dans **Mettre en cache les symboles à partir du serveur de symboles vers ce répertoire**, tapez le chemin du dossier créé à l’étape 1 ; par exemple :  
  
     **C:\SymbolCache**  
  
     Vous pouvez également cliquer sur le bouton de sélection (**...**), puis sélectionner un répertoire dans la boîte de dialogue **Rechercher un dossier**.  
  
## <a name="see-also"></a>Voir aussi  
 [Configuration de sessions de performance](../profiling/configuring-performance-sessions.md)   
 [Guide pratique pour sérialiser les informations de symboles](../profiling/how-to-serialize-symbol-information.md)