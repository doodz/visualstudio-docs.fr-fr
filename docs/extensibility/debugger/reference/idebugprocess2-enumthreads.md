---
title: IDebugProcess2::EnumThreads | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess2::EnumThreads
helpviewer_keywords: IDebugProcess2::EnumThreads
ms.assetid: 05677385-7a7f-4545-8438-af00dde85db0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6e1cc33d1a84f5f8a3cd186b148f57e296a350f4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocess2enumthreads"></a>IDebugProcess2::EnumThreads
Récupère une liste de tous les threads en cours d’exécution dans le processus.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumThreads(  
   IEnumDebugThreads2** ppEnum  
);  
```  
  
```csharp  
int EnumThreads(  
   out IEnumDebugThreads2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ppEnum`  
 [out] Retourne un [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md) objet qui contient une liste de tous les threads dans tous les programmes dans le processus.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Remarques  
 Cette méthode énumère les threads en cours d’exécution de chaque programme et les combine ensuite en une vue des threads de processus. Un seul thread peut exécuter plusieurs programmes. Cette méthode énumère ce thread qu’une seule fois.  
  
 Cette méthode présente une liste de threads du processus sans doublons. Sinon, pour énumérer les threads en cours d’exécution dans un programme particulier, utilisez le [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) (méthode).  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)