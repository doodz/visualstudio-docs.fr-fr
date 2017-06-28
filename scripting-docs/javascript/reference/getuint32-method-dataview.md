---
title: "getUint32, m&#233;thode (DataView) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 266ee6b6-c0b6-417e-a64b-c8cda48fde86
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# getUint32, m&#233;thode (DataView)
Obtient la valeur Uint32 au niveau de l'offset d'octet spécifié à partir du début de la vue.  Il n'existe aucune contrainte d'alignement ; les valeurs multioctets peuvent être extraite à partir de n'importe quel offset.  
  
## Syntaxe  
  
```  
var testInt = dataView.get Uint32 (byteOffset, littleEndian);   
```  
  
## Paramètres  
 `testInt`  
 Obligatoire.  Valeur Uint32 retournée par la méthode.  
  
 `byteOffset`  
 Emplacement dans la mémoire tampon auquel la valeur doit être récupérée.  
  
 `littleEndian`  
 Facultatif.  Si la valeur est False ou Undefined, une valeur avec primauté des octets de poids fort \(big\-endian\) doit être lue, sinon une valeur avec primauté des octets de poids faible \(little\-endian\) doit être lue.  
  
## Notes  
 Ces méthodes lèvent une exception si elles doivent lire au\-delà de la fin de la vue.  
  
## Exemple  
 L'exemple suivant montre comment obtenir le premier Uint32 dans le DataView.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getUint32(0));  
        }  
    }  
  
```  
  
## Configuration requise  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]