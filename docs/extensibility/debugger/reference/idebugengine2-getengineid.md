---
title: IDebugEngine2::GetEngineID | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine2::GetEngineID
helpviewer_keywords: IDebugEngine2::GetEngineID
ms.assetid: 0d5674c8-a9b9-4b72-8211-d2d68695775a
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 008c3cb2f2c4f8e12eedbae347515099524da2c0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugengine2getengineid"></a>IDebugEngine2::GetEngineID
Obtient le GUID du moteur de débogage (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetEngineID(   
   GUID* pguidEngine  
);  
```  
  
```csharp  
int GetEngineID(   
   out Guid pguidEngine  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pguidEngine`  
 [out] Retourne le GUID de la DE.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="remarks"></a>Remarques  
 Voici quelques exemples de type GUID `guidScriptEng`, `guidNativeEng`, ou `guidSQLEng`. Des moteurs de débogage créera leur propre GUID d’identification.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment implémenter cette méthode pour une simple `CEngine` objet qui implémente le [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) interface.  
  
```cpp  
HRESULT CEngine::GetEngineId(GUID *pguidEngine){    
   if (pguidEngine) {    
      // Set pguidEngine to guidBatEng, as defined in the Batdbg.idl file.    
      // Other languages would require their own guidDifferentEngine to be  
      //defined in the Batdbg.idl file.    
      *pguidEngine = guidBatEng;    
      return NOERROR; // This is typically S_OK.    
   } else {  
      return E_INVALIDARG;    
   }    
}    
```  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)