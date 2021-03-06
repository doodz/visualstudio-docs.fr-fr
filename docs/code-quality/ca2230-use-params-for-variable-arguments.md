---
title: "CA2230 : Utilisez params pour les arguments de variables | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 10920c4ff9083b52e2d35f7fa151644b89bb1102
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230 : Utilisez le mot clé params pour les arguments de variables
|||  
|-|-|  
|TypeName|UseParamsForVariableArguments|  
|CheckId|CA2230|  
|Catégorie|Microsoft.Usage|  
|Modification avec rupture|Rupture|  
  
## <a name="cause"></a>Cause  
 Un type public ou protégé contient une méthode publique ou protégée qui utilise le `VarArgs` convention d’appel.  
  
## <a name="rule-description"></a>Description de la règle  
 Le `VarArgs` convention d’appel est utilisée avec certaines définitions de méthode qui acceptent un nombre variable de paramètres. Une méthode à l’aide de la `VarArgs` convention d’appel n’est pas Common Language Specification (CLS) conforme et ne peut pas être accessible entre les langages de programmation.  
  
 En c#, le `VarArgs` convention d’appel est utilisé lors de la liste de paramètres d’une méthode se termine par le `__arglist` (mot clé). Visual Basic ne prend pas en charge la `VarArgs` convention d’appel et Visual C++ permet son utilisation uniquement dans le code non managé qui utilise les points de suspension `...` notation.  
  
## <a name="how-to-fix-violations"></a>Comment corriger les violations  
 Pour corriger une violation de cette règle en c#, utilisez le [params](/dotnet/csharp/language-reference/keywords/params) (mot clé) au lieu de `__arglist`.  
  
## <a name="when-to-suppress-warnings"></a>Quand supprimer les avertissements  
 Ne supprimez aucun avertissement de cette règle.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre deux méthodes, qui enfreint la règle et qui satisfait à la règle.  
  
 [!code-csharp[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Reflection.CallingConventions?displayProperty=fullName>   
 [Indépendance du langage et composants indépendants du langage](http://msdn.microsoft.com/Library/4f0b77d0-4844-464f-af73-6e06bedeafc6)