---
title: IDebugApplication110::SynchronousCallInMainThread | Documents Microsoft
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IDebugApplication110::SynchronousCallInMainThread
ms.assetid: 57475ae5-1520-45ef-800d-ccfc6235a5d1
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef52ebfe8bfccecc0eea2383787a5b2698a5ce5f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplication110synchronouscallinmainthread"></a>IDebugApplication110::SynchronousCallInMainThread
Effectue un appel synchrone sur le thread principal.  
  
> [!IMPORTANT]
>  [IDebugApplication110 (Interface)](../../winscript/reference/idebugapplication110-interface.md) est implémentée par PDM version v11.0 et supérieures. Trouvée dans activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SynchronousCallInMainThread([in] IDebugThreadCall* pptc, [in] DWORD_PTR dwParam1, [in] DWORD_PTR dwParam2, [in] DWORD_PTR dwParam3);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pptc`  
 Le [idebugthreadcall, Interface](../../winscript/reference/idebugthreadcall-interface.md) objet à appeler.  
  
 `dwParam1`  
 Le premier paramètre de l’appel.  
  
 `dwParam1`  
 Le premier paramètre de l’appel.  
  
 `dwParam2`  
 Le deuxième paramètre de l’appel.  
  
 `dwParam3`  
 Le troisième paramètre de l’appel.  
  
## <a name="see-also"></a>Voir aussi  
 [Interface IDebugApplication110](../../winscript/reference/idebugapplication110-interface.md)