---
title: "Erreur : Une vérification de sécurité a échoué, car le Service d’administration IIS n’a pas répondu | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.iis_not_responding
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
ms.assetid: 6060e94e-71dc-49f2-bb59-2584216eadbf
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5bc147c979357934d68692ea863c665422c84b34
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="error-a-security-check-failed-because-the-iis-admin-service-did-not-respond"></a>Erreur : une vérification de la sécurité a échoué, car le service de l'administration IIS n'a pas répondu
Cette erreur se produit lorsque le service IIS Admin ne répond pas. Il s'agit généralement d'un problème relatif à l'installation IIS. Tout d’abord, vérifiez que le service est en cours d’exécution à l’aide de la **Services** outil à partir de **outils d’administration**.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Réinstallez IIS, à l’aide de la **Ajout / Suppression de programmes** le panneau de configuration.  
  
-   ou  
  
-   Supprimez IIS de votre ordinateur, à l'aide de l'application Ajout/Suppression de programmes du Panneau de configuration. Si vous avez supprimé IIS et que les problèmes persistent, examinez le Registre et assurez-vous que cette clé n'existe plus :  
  
    ```  
    HKEY_CLASSES_ROOT\CLSID\{A9E69610-B80D-11D0-B9B9-00A0C922E750}  
    ```  
  
     ou  
  
-   Désactivez le service de l'administration IIS, à l'aide du panneau de configuration Outils d'administration. Cela permet de désactiver IIS sur votre ordinateur.  
  
     Après avoir exécuté l'une de ces trois opérations, redémarrez votre ordinateur.  
  
     Pour plus d'informations, consultez la documentation IIS.  
  
## <a name="see-also"></a>Voir aussi  
 [Débogage d’applications web : erreurs et dépannage](../debugger/debugging-web-applications-errors-and-troubleshooting.md)