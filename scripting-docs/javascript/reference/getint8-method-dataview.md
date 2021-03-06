---
title: "getint8, méthode (DataView) | Documents Microsoft"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 867eefa0-f2e0-44b9-85bc-efb849d55138
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4963cb1b407b964b082daa10660fe812dcb700b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
# <a name="getint8-method-dataview"></a>getInt8, méthode (DataView)
Obtient la valeur Int8 à l’offset d’octet spécifié à partir du début de la vue. Il n’existe aucune contrainte d’alignement ; les valeurs sur plusieurs octets peuvent être lues à partir de n’importe quel décalage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
var testInt = dataView.getInt8(byteOffset);   
```  
  
## <a name="parameters"></a>Paramètres  
 `testInt`  
 Obligatoire. La valeur Int8 qui est retournée à partir de la méthode.  
  
 `byteOffset`  
 L’emplacement de la mémoire tampon à laquelle la valeur doit être récupérée.  
  
## <a name="remarks"></a>Remarques  
 Ces méthodes déclenchent une exception si elles sont en lecture au-delà de la fin de la vue.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment obtenir le premier Int8 du DataView.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getInt8(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Spécifications  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]