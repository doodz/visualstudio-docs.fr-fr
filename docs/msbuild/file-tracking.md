---
title: Suivi des fichiers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: msbuild, file tracking
ms.assetid: e6c66ac0-3464-451f-9192-3b98dca21b4a
caps.latest.revision: "6"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: a43c651b6f39e53b77eabe261c67ad7ca0fdcf78
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="file-tracking"></a>Suivi des fichiers
Le suivi des fichiers journalise les appels au système de fichiers Windows pour un processus et ses processus enfants. En appelant les fonctions listées ci-dessous, les programmes contrôlent le moment auquel activer et désactiver la journalisation, et spécifient le fichier journal à utiliser.  
  
## <a name="in-this-section"></a>Dans cette section  
 [EndTrackingContext](../msbuild/endtrackingcontext.md)  
 Arrête le suivi dans le contexte actuel.  
  
 [ResumeTracking](../msbuild/resumetracking.md)  
 Redémarre le suivi après un appel à [SuspendTracking](../msbuild/suspendtracking.md).  
  
 [SetThreadCount](../msbuild/setthreadcount.md)  
 Définit le nombre de threads à utiliser pour le suivi.  
  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)  
 Démarre un nouveau contexte de suivi.  
  
 [StartTrackingContextWithRoot](../msbuild/starttrackingcontextwithroot.md)  
 Démarre un nouveau contexte de suivi avec une racine spécifiée.  
  
 [StopTrackingAndCleanup](../msbuild/stoptrackingandcleanup.md)  
 Termine le suivi et libère les ressources utilisées.  
  
 [SuspendTracking](../msbuild/suspendtracking.md)  
 Suspend temporairement le suivi.  
  
 [WriteAllTLogs](../msbuild/writealltlogs.md)  
 Écrit les journaux de suivi pour tous les contextes.  
  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)  
 Écrit le journal de suivi du contexte actuel.