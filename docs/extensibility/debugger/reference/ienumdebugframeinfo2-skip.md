---
title: IEnumDebugFrameInfo2::Skip | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFrameInfo2::Skip
helpviewer_keywords: IEnumDebugFrameInfo2::Skip
ms.assetid: 68cd3948-022a-41ad-bd9f-9ab776cf6248
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3a03f109c52b6c60ef4ed1016385b62f24b0cbcf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugframeinfo2skip"></a>IEnumDebugFrameInfo2::Skip
Ignore le nombre spécifié d’éléments.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `celt`  
 [in] Nombre d’éléments à ignorer.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`. Retourne `S_FALSE` si `celt` est supérieur au nombre d’éléments restants ; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Remarques  
 Si `celt` spécifie une valeur supérieure au nombre d’éléments restants, l’énumération est définie à la fin et `S_FALSE` est retourné.  
  
## <a name="see-also"></a>Voir aussi  
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)