---
title: IDiaSymbol::get_indirectVirtualBaseClass | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_indirectVirtualBaseClass method
ms.assetid: 853b5c6f-e1cb-4675-ad36-9ee16e3341c3
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9ed9a0893d88178cf7d335dad028050ecf30d9c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetindirectvirtualbaseclass"></a>IDiaSymbol::get_indirectVirtualBaseClass
Récupère un indicateur qui spécifie si le type de données défini par l’utilisateur est une classe de base virtuelle indirecte.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_indirectVirtualBaseClass (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pRetVal`  
 [out] Retourne `TRUE` si le type de données défini par l’utilisateur est une classe de base virtuelle indirecte ; sinon, retourne `FALSE`.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne `S_FALSE` ou code d’erreur.  
  
> [!NOTE]
>  La valeur de retour `S_FALSE` signifie que la propriété n’est pas disponible pour le symbole.  
  
## <a name="requirements"></a>Spécifications  
  
|Spécification|Description|  
|-----------------|-----------------|  
|En-tête :|dia2.h|  
|Version :|DIA SDK v7.0|  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)