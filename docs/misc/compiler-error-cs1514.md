---
title: "Erreur du compilateur CS1514 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1514"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1514"
ms.assetid: 61c25e0e-84b1-4b94-b790-ef1e4ff9fc4e
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Erreur du compilateur CS1514
{ attendue  
  
 Le compilateur attendait une accolade ouvrante \(`{`\) qui n’a pas été trouvée.  
  
 L’exemple suivant génère l’erreur CS1514 :  
  
```  
// CS1514.cs namespace x // CS1514, no open curly brace  
```