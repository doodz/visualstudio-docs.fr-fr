---
title: "Code mixte et informations manquantes dans la fenêtre Pile des appels | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97c7cd3588edbb7b07c5eaed25df07c882805d73
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>Code mixte et informations manquantes dans la fenêtre Pile des appels
En raison de différences entre la pile des appels du code managé et celle du code natif, le débogueur ne peut pas toujours afficher la pile des appels complète en cas de types de code mixtes. Lorsque le code natif appelle du code managé, vous pouvez noter les divergences suivantes dans le **pile des appels** fenêtre :  
  
-   Le frame natif immédiatement au-dessus du code managé peut-être être absent dans la **pile des appels** fenêtre. Pour plus d’informations, consultez [Comment : pas à pas sortant du Code managé lorsque les Frames natifs sont absents de la fenêtre Pile des appels](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md).  
  
-   Pour les applications en mode mixte lancées en dehors du débogueur, la **pile des appels** fenêtre peut afficher uniquement le code managé et aucun des frames natifs ne sera visible.  
  
 Ces deux situations sont assez rares. Dans la plupart des appels natifs au code managé, les piles d'appels apparaissent correctement.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour utiliser la fenêtre Pile des appels](../debugger/how-to-use-the-call-stack-window.md)