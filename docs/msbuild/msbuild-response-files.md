---
title: "Fichiers réponse MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- response files, MSBuild
- MSBuild, response files
- MSBuild, .rsp files
- .rsp files
ms.assetid: 9f53987b-20ee-470a-ab62-fce997bb5e15
caps.latest.revision: "3"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: a9ceab64ec0009dd143f42e1b94538690780f1bb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-response-files"></a>Fichiers réponse MSBuild
Les fichiers réponse (.rsp) sont des fichiers texte qui contiennent des commutateurs de ligne de commande MSBuild.exe. Les commutateurs peuvent se trouver chacun sur une ligne distincte ou se trouver tous sur une même ligne. Les lignes de commentaire sont précédées d’un symbole **#**. Le commutateur **@** est utilisé pour passer un autre fichier réponse à MSBuild.exe.  
  
 Le fichier réponse automatique est un fichier .rsp spécial que MSBuild.exe utilise automatiquement lors de la génération d’un projet. Ce fichier (MSBuild.rsp) doit se trouver dans le même répertoire que MSBuild.exe, sinon il sera introuvable. Vous pouvez modifier ce fichier pour spécifier des commutateurs de ligne de commande par défaut à MSBuild.exe. Par exemple, si vous utilisez le même enregistreur d’événements chaque fois que vous générez un projet, vous pouvez ajouter le commutateur **/logger** au fichier MSBuild.rsp. Ainsi, MSBuild.exe utilise l’enregistreur d’événements chaque fois qu’un projet est généré.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur MSBuild](../msbuild/msbuild-reference.md)   
 [Informations de référence sur la ligne de commande](../msbuild/msbuild-command-line-reference.md)