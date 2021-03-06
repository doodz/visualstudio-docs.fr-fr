---
title: Fonction de SccIsMultiCheckoutEnabled | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccIsMultiCheckoutEnabled
helpviewer_keywords: SccIsMultiCheckoutEnabled function
ms.assetid: 6721639d-e475-4766-81b5-ee40a280fc70
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6ca1f26078a590ae2034218c5df4a74b66fa2449
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="sccismulticheckoutenabled-function"></a>SccIsMultiCheckoutEnabled (fonction)
Cette fonction vérifie si le plug-in de contrôle de code source autorise les extractions multiples sur un fichier.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccIsMultiCheckoutEnabled(  
   LPVOID pContext,  
   LPBOOL pbMultiCheckout  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 pContext  
 [in] La structure de contexte plug-in de contrôle de code source.  
  
 pbMultiCheckout  
 [out] Spécifie si les extractions multiples sont activées pour ce projet (différente de zéro signifie que les extractions multiples sont pris en charge).  
  
## <a name="return-value"></a>Valeur de retour  
 L’implémentation de plug-in de contrôle de source de cette fonction est censée retourner l’une des valeurs suivantes :  
  
|Valeur|Description|  
|-----------|-----------------|  
|SCC_OK|La vérification a réussi.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Erreur non spécifique.|  
  
## <a name="remarks"></a>Remarques  
 L’IDE effectue deux vérifications pour déterminer si les fichiers peuvent être extraits simultanément par plusieurs utilisateurs. Tout d’abord, le système de contrôle de code source doit prendre en charge les extractions multiples. Le plug-in de contrôle de code source peut spécifier cette fonctionnalité lors de l’initialisation en spécifiant le `SCC_CAP_MULTICHECKOUT`. Par la suite, un deuxième contrôle, comme l’IDE appelle cette fonction pour déterminer si le projet actif prend en charge les extractions multiples. Si les extractions multiples sont pris en charge pour le projet sélectionné, le plug-in retourne la réussite de code et définit `pbMultiCheckout` à différente de zéro (`TRUE`) ou `FALSE`.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions d’API du plug-in de contrôle de code source](../extensibility/source-control-plug-in-api-functions.md)