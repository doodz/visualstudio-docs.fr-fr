---
title: BasicType | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: BasicType enumeration
ms.assetid: 19ae53ba-cd6e-47b6-9f94-27ae663ce955
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f93fa1380dbb2d7623cddec3780593cd50513f2a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="basictype"></a>BasicType
Spécifie le type de base du symbole.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum BasicType {   
   btNoType   = 0,  
   btVoid     = 1,  
   btChar     = 2,  
   btWChar    = 3,  
   btInt      = 6,  
   btUInt     = 7,  
   btFloat    = 8,  
   btBCD      = 9,  
   btBool     = 10,  
   btLong     = 13,  
   btULong    = 14,  
   btCurrency = 25,  
   btDate     = 26,  
   btVariant  = 27,  
   btComplex  = 28,  
   btBit      = 29,  
   btBSTR     = 30,  
   btHresult  = 31  
};  
```  
  
## <a name="elements"></a>Éléments  
 btNoType  
 Aucun type de base est spécifié.  
  
 btVoid  
 Type de base est un `void`.  
  
 btChar  
 Type de base est un `char` (type C/C++).  
  
 btWChar  
 Type de base est un caractère (Unicode) large (`WCHAR`).  
  
 btInt  
 Type de base est `signed int` (type C/C++).  
  
 btUInt  
 Type de base est `unsigned int` (type C/C++).  
  
 btFloat  
 Type de base est un nombre à virgule flottante (`FLOAT`).  
  
 btBCD  
 Type de base est un nombre décimal codé en binaire (`BCD`).  
  
 btBool  
 Type de base est une valeur booléenne (`BOOL`).  
  
 btLong  
 Type de base est un `long int` (type C/C++).  
  
 btULong  
 Type de base est un `unsigned long int` (type C/C++).  
  
 btCurrency  
 Type de base est la devise.  
  
 btDate  
 Type de base est la date/heure (`DATE`).  
  
 btVariant  
 Type de base est une structure de type de variable (`VARIANT`).  
  
 btComplex  
 Type de base est un nombre complexe.  
  
 btBit  
 Type de base est un bit.  
  
 btBSTR  
 Type de base est une chaîne binaire ou de base (`BSTR`).  
  
 btHresult  
 Type de base est un `HRESULT`.  
  
## <a name="remarks"></a>Remarques  
 Les valeurs de cette énumération sont retournées par la [IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md) (méthode).  
  
## <a name="requirements"></a>Spécifications  
 En-tête : cvconst.h  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations et Structures](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)