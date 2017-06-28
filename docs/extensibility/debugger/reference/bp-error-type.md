---
title: BP_ERROR_TYPE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_ERROR_TYPE
helpviewer_keywords:
- BP_ERROR_TYPE enumeration
ms.assetid: c483eaab-db29-46de-bfdb-5c2a9a9cfb68
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 07248d28d34373176f9897472c39c0756012da59
ms.lasthandoff: 02/22/2017

---
# <a name="bperrortype"></a>BP_ERROR_TYPE
Spécifie le type d’erreur d’un point d’arrêt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
typedef DWORD BP_ERROR_TYPE;  
```  
  
```c#  
public enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
```  
  
## <a name="members"></a>Membres  
 BPET_NONE  
 Ne spécifie aucune erreur de point d’arrêt.  
  
 BPET_TYPE_WARNING  
 Spécifie une erreur de point d’arrêt d’avertissement de style.  
  
 BPET_TYPE_ERROR  
 Spécifie une erreur de point d’arrêt de style d’erreur.  
  
 BPET_SEV_HIGH  
 Spécifie une erreur de point d’arrêt à gravité élevée.  
  
 BPET_SEV_GENERAL  
 Spécifie une erreur de point d’arrêt de gravité moyenne.  
  
 BPET_SEV_LOW  
 Spécifie une erreur de point d’arrêt de faible gravité.  
  
 BPET_TYPE_MASK  
 Spécifie une erreur de point d’arrêt de masque de style.  
  
 BPET_SEV_MASK  
 Spécifie une erreur de point d’arrêt de la gravité de type masque.  
  
 BPET_GENERAL_WARNING  
 Spécifie une erreur de point d’arrêt général de type avertissement.  
  
 BPET_GENERAL_ERROR  
 Spécifie une erreur de point d’arrêt de style d’erreur générale.  
  
 BPET_ALL  
 Spécifie tous les types d’erreur de point d’arrêt.  
  
## <a name="remarks"></a>Remarques  
 Ces valeurs peuvent être combinées avec une opération de bits `OR` et utilisé pour le `dwType` membre de la [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) structure. Passé en tant que paramètre à la [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) (méthode).  
  
 Un type d’erreur de point d’arrêt se compose d’un type et un niveau de gravité. Cela signifie qu’un type d’erreur de point d’arrêt n’est jamais simplement un type (par exemple, `BPET_TYPE_ERROR`,) ou un niveau de gravité (par exemple, `BPET_SEV_GENERAL`) par elle-même. `BPET_GENERAL_WARNING`et `BPET_GENERAL_ERROR` fournissent des valeurs prédéfinies pour les points d’arrêt générales de l’erreur et d’avertissement.  
  
## <a name="requirements"></a>Spécifications  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)