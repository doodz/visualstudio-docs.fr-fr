---
title: IDiaDataSource::openSession | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 72fa36bd077a08484c225e1349134929e541d074
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
Ouvre une session pour l’interrogation des symboles.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 ppSession  
 [out] Retourne un [IDiaSession](../../debugger/debug-interface-access/idiasession.md) objet représentant la session ouverte.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne `S_OK`; sinon, retourne un code d’erreur. Le tableau suivant montre les valeurs de retournés possibles pour cette méthode.  
  
|Valeur|Description|  
|-----------|-----------------|  
|E_UNEXPECTED|Le [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md) objet n’a pas déjà été initialisé avec une source de symboles.|  
|E_INVALIDARG|Non valide `ppSession` paramètre.|  
|E_OUTOFMEMORY|Mémoire insuffisante pour ouvrir la session.|  
  
## <a name="remarks"></a>Remarques  
 Cette méthode ouvre un [IDiaSession](../../debugger/debug-interface-access/idiasession.md) objet pour une source de données.  
  
 `IDiaSession`objets d’implémenter des requêtes dans la source de données. Une session gère un espace d’adressage pour chaque ensemble de symboles de débogage. Si le fichier .exe ou .dll décrit par les symboles de source de données est active dans la zone Adresse plusieurs plages (par exemple, étant donné que plusieurs processus ont chargé), puis une session pour chaque plage d’adresses doit être utilisée.  
  
## <a name="example"></a>Exemple  
  
```C++  
IDiaSession* pSession;  
HRESULT hr = pSource->openSession( &pSession );  
if (FAILED(hr))  
{  
   // report error  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Vue d’ensemble](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [Interrogation du fichier .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)