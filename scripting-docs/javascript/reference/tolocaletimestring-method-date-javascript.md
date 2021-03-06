---
title: "toLocaleTimeString, méthode (Date) (JavaScript) | Documents Microsoft"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toLocaleTimeString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toLocaleTimeString method
ms.assetid: 8ad75bf5-864c-4a2a-be90-220e87dce172
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77d8ee8fb6757b13da22a3cf3a59d28a105292cb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
# <a name="tolocaletimestring-method-date-javascript"></a>toLocaleTimeString, méthode (Date) (JavaScript)
Retourne une heure en tant que valeur de chaîne adaptée aux paramètres régionaux actuels de l'environnement hôte ou à des paramètres régionaux spécifiés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.toLocaleTimeString([locales][, options])  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dateObj`  
 Obligatoire. Objet `Date`.  
  
 `locales`  
 Facultatif. Tableau de chaînes de paramètres régionaux qui contiennent une ou plusieurs balises de langue ou de paramètres régionaux. Si vous incluez plusieurs chaînes de paramètres régionaux, répertoriez-les dans l'ordre de priorité décroissant afin que la première entrée soit la valeur par défaut. Si vous omettez ce paramètre, les paramètres régionaux par défaut du runtime JavaScript sont utilisés.  
  
 `options`  
 Facultatif. Objet qui contient une ou plusieurs propriétés qui spécifient des options de comparaison.  
  
## <a name="remarks"></a>Remarques  
 À partir d'Internet Explorer 11, `toLocaleTimeString` utilise `Intl.DateTimeFormat` en interne pour mettre en forme l'heure, ce qui ajoute la prise en charge des paramètres `locales` et `options`. Pour plus d’informations sur ces paramètres, consultez [Intl.DateTimeFormat](../../javascript/reference/intl-datetimeformat-object-javascript.md).  
  
> [!IMPORTANT]
>  Les paramètres `locales` et `options` ne sont pas pris en charge dans tous les modes de document et les versions de navigateur. Pour plus d'informations, consultez la section Configuration requise.  
  
 Lorsque vous utilisez `toLocaleTimeString` en mode de document standard Internet Explorer 10, dans les modes de document précédents et en mode Quirks :  
  
-   Elle retourne une valeur de chaîne qui contient une heure dans le fuseau horaire actuel.  
  
-   L'heure retournée est au format par défaut des paramètres régionaux actuels de l'environnement hôte.  
  
 Si vous omettez le paramètre `locales`, vous ne pouvez pas vous fier à la valeur de retour de cette méthode dans un script, car elle varie d'un ordinateur à l'autre. Dans ce scénario, utilisez la méthode uniquement au texte de format d’affichage - jamais dans le cadre d’un calcul.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment utiliser la méthode `toLocaleTimeString` avec des options de comparaison et de paramètres régionaux spécifiées.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleTimeString("en-US"));  
document.write(date.toLocaleTimeString("ja-JP"));  
document.write(date.toLocaleTimeString("ar-SA", options));  
document.write(date.toLocaleTimeString("hi-IN", options));  
  
// Output:  
// ‎‎6‎:‎00‎:‎00‎ ‎AM ‎   
// 6‎:‎00‎:‎00‎  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤ ٠٦‎:‎٠٠‎:‎٠٠‎ ‎ص  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013 06:00:00  
  
```  
  
## <a name="requirements"></a>Spécifications  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 Paramètres `locales` et `options` :  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [toTimeString, méthode (Date)](../../javascript/reference/totimestring-method-date-javascript.md)   
 [Méthode toLocaleDateString (Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)