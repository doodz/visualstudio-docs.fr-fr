---
title: IDebugSymbolProviderDirect::GetMethodFromAddress | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugSymbolProviderDirect::GetMethodFromAddress
- GetMethodFromAddress
ms.assetid: 33ffd197-1221-41bc-a9f6-f133ebdcb783
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a6a65a2a77ef0832acf8ce8af6b8c0181aa50989
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugsymbolproviderdirectgetmethodfromaddress"></a>IDebugSymbolProviderDirect::GetMethodFromAddress
Récupère les informations sur la méthode à l’adresse de débogage spécifiés.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMethodFromAddress(  
   IDebugAddress* pAddress,  
   GUID*          pGuid,  
   DWORD*         pAppID,  
   _mdToken*      pTokenClass,  
   _mdToken*      pTokenMethod,  
   DWORD*         pdwOffset,  
   DWORD*         pdwVersion  
);  
```  
  
```csharp  
int GetMethodFromAddress(  
   IDebugAddress pAddress,  
   out Guid      pGuid,  
   out uint      pAppID,  
   out uint      pTokenClass,  
   out uint      pTokenMethod,  
   out uint      pdwOffset,  
   out uint      pdwVersion  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pAddress`  
 [in] Débogage d’adresse qui est représenté par le [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) interface.  
  
 `pGuid`  
 [out] Identificateur unique du module.  
  
 `pAppID`  
 [out] Identificateur du domaine d’application.  
  
 `pTokenClass`  
 [out] Jeton qui représente la classe conteneur.  
  
 `pTokenMethod`  
 [out] Jeton qui représente le module.  
  
 `pdwOffset`  
 [out] Un offset en octets à partir du début de la `pAddress` paramètre.  
  
 `pdwVersion`  
 [out] Numéro de version de la méthode.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)