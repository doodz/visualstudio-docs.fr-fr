---
title: DOCCONTEXT_COMPARE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DOCCONTEXT_COMPARE
helpviewer_keywords: DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2074e5abe688ecb8f796099cf23309ec0cfe954d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
Spécifie les critères pour la comparaison de deux contextes de document.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```csharp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## <a name="members"></a>Membres  
 DOCCONTEXT_EQUAL  
 Recherche le premier contexte de document dans la liste qui est égale au contexte du document cible.  
  
 DOCCONTEXT_LESS_THAN  
 Recherche le premier contexte de document dans la liste qui est inférieur au contexte du document cible.  
  
 DOCCONTEXT_GREATER_THAN  
 Recherche le premier contexte de document dans la liste supérieure dans le contexte du document cible.  
  
 DOCCONTEXT_SAME_DOCUMENT  
 Recherche le premier contexte de document dans la liste qui se trouve dans le même document que le contexte du document cible.  
  
## <a name="remarks"></a>Remarques  
 Est passé comme argument à la [comparer](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) (méthode).  
  
 Ces valeurs sont utilisées pour spécifier des critères de comparaison pour rechercher le premier contexte de document dans une liste. Un contexte de document reçoit une liste de contextes de document à comparer lui-même, par rapport à la `IDebugDocumentContext2::Compare` (méthode). Le premier contexte de document dans la liste pour laquelle l’opérateur de comparaison est `true` est alors retournée.  
  
## <a name="requirements"></a>Spécifications  
 En-tête : msdbg.h  
  
 Namespace : Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly : Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Voir aussi  
 [Énumérations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)