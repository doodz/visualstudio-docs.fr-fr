---
title: "VCMessage, tâche | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.task.vcmessage
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- VCMessage task (MSBuild (Visual C++))
- MSBuild (Visual C++), VCMessage task
ms.assetid: 956675fd-05dc-40b4-856f-616145103498
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 16ed7f4207a65915afbf18a496a0152e04e9a8d0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="vcmessage-task"></a>VCMessage, tâche
Journalise les messages d’avertissement et d’erreur lors de la génération.  
  
## <a name="remarks"></a>Remarques  
 Cette tâche permet d’implémenter MSBuild pour Visual C++ et n’est pas destinée à être appelée par l’utilisateur. Pour plus d'informations, consultez <xref:Microsoft.Build.Utilities.TaskLoggingHelper>.  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche **VCMessage**.  
  
|Paramètre|Description|  
|---------------|-----------------|  
|**Arguments**|Paramètre de **chaîne** facultatif.<br /><br /> Liste de messages (séparés par des points-virgules) devant être affichée.|  
|**Code**|Paramètre **String** obligatoire.<br /><br /> Numéro d’erreur qui qualifie le message.|  
|**Type**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie le type de message à émettre. Spécifie soit `"Warning"` pour émettre un message d’avertissement, soit `"Error"` pour émettre un message d’erreur.|  
  
## <a name="see-also"></a>Voir aussi  
 [Task Reference (Informations de référence sur les tâches MSBuild)](../msbuild/msbuild-task-reference.md)