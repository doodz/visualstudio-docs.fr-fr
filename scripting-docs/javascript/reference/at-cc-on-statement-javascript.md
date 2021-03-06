---
title: '@cc_onInstruction (JavaScript) | Documents Microsoft'
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '@cc_on_JavaScriptKeyword'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional compilation, activating
- '@cc_on statement'
- '@set statement'
- '@if statement'
ms.assetid: fdeda7ee-b9f4-4e52-8aa2-21c90c02a332
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7e993d5bc8302931a5722495da70612e79f7dfd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
# <a name="ccon-statement-javascript"></a>@cc_onInstruction (JavaScript)
Active la prise en charge de la compilation conditionnelle dans les commentaires d'un script.  
  
> [!WARNING]
>  La compilation conditionnelle n'est prise en charge ni par le mode standard d'Internet Explorer 11, ni par les applications [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)]. La compilation conditionnelle est prise en charge par le mode standard d'Internet Explorer 10 et toutes les versions antérieures.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
@cc_on   
```  
  
## <a name="remarks"></a>Remarques  
 L'instruction `@cc_on` active la prise en charge de la compilation conditionnelle dans les commentaires d'un script.  
  
 En revanche, elles sont peu employées dans des scripts écrits pour des pages ASP ou ASP.NET, ou des programmes en ligne de commande, car les fonctionnalités des compilateurs peuvent être déterminées par d'autres méthodes.  
  
 Lorsque vous écrivez un script pour une page Web, placez toujours le code de compilation conditionnelle dans des commentaires. Dès lors, les hôtes qui ne prennent pas en charge la compilation conditionnelle peuvent l'ignorer.  
  
 Il est fortement recommandé d'utiliser l'instruction `@cc_on` dans un commentaire, afin que les navigateurs qui ne prennent pas en charge la compilation conditionnelle acceptent votre script comme une syntaxe valide :  
  
 Une instruction `@if` ou `@set` placée en dehors d'un commentaire active également la compilation conditionnelle.  
  
## <a name="example"></a>Exemple  
 L'exemple ci-dessous illustre l'utilisation de l'instruction `@cc_on`.  
  
```JavaScript  
/*@cc_on @*/  
/*@  
    document.write("JavaScript version: " + @_jscript_version + ".");  
    document.write("<br />");  
    @if (@_win32)  
        document.write("Running on the 32-bit version of Windows.");  
    @elif (@_win16)  
        document.write("Running on the 16-bit version of Windows.");  
    @else  
        document.write("Running on a different operating system.");  
    @end  
@*/  
```  
  
## <a name="requirements"></a>Spécifications  
 Prise en charge dans toutes les versions d'Internet Explorer, mais pas dans les applications [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Compilation conditionnelle](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Variables de Compilation conditionnelle](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@ifInstruction](../../javascript/reference/at-if-statement-javascript.md)   
 [@set Instruction](../../javascript/reference/at-set-statement-javascript.md)