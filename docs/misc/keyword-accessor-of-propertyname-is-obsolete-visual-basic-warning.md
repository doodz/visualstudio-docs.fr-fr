---
title: "L’accesseur &#39;&lt;mot cl&#233;&gt;&#39; de &#39;&lt;nom_propri&#233;t&#233;&gt;&#39; est obsol&#232;te (avertissement Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40020"
  - "bc40020"
helpviewer_keywords: 
  - "BC40020"
ms.assetid: 005440f4-6e82-421c-b2ce-9c5139325bac
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# L’accesseur &#39;&lt;mot cl&#233;&gt;&#39; de &#39;&lt;nom_propri&#233;t&#233;&gt;&#39; est obsol&#232;te (avertissement Visual Basic)
Une instruction essaie de lire ou d’écrire une propriété pour laquelle la procédure correspondante a été marquée avec l’attribut <xref:System.ObsoleteAttribute> et la directive pour la traiter comme un avertissement.  
  
 Vous pouvez marquer un élément de programmation comme n’étant plus utilisés en lui appliquant <xref:System.ObsoleteAttribute>. Dans ce cas, vous pouvez affecter à la propriété <xref:System.ObsoleteAttribute.IsError%2A> de l’attribut la valeur `True` ou `False`. Si vous lui affectez la valeur `True`, le compilateur traite une tentative d’utilisation de l’élément comme une erreur. Si vous lui affectez la valeur `False`, ou si vous laissez la valeur par défaut `False`, le compilateur émet un avertissement en cas de tentative d’utilisation de l’élément.  
  
 Par défaut, ce message est un avertissement, car la propriété <xref:System.ObsoleteAttribute.IsError%2A> de <xref:System.ObsoleteAttribute> a la valeur `False`. Pour plus d’informations sur le masquage des avertissements ou le traitement des avertissements en tant qu’erreurs, consultez [Configuration d'avertissements en Visual Basic](../ide/configuring-warnings-in-visual-basic.md).  
  
 **ID d’erreur :** BC40020  
  
### Pour corriger cette erreur  
  
1.  Assurez\-vous que le nom de la propriété est orthographié correctement dans la référence du code source.  
  
2.  Évitez d’accéder à la propriété de la manière \(lecture ou écriture\) dont ce message a été généré.  
  
## Voir aussi  
 [NOT IN BUILD : Attributs utilisés en Visual Basic](http://msdn.microsoft.com/fr-fr/22231318-8a40-49af-9245-e0aab723563b)   
 [NOT IN BUILD : Application des attributs](http://msdn.microsoft.com/fr-fr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [Procédures de propriété](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)