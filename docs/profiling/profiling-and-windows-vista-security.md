---
title: "Profilage et sécurité Windows Vista | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Profiling Tools,security
- performance tools, security
ms.assetid: 842112fc-b886-4801-8cd7-a25b314b0393
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ac59d9cb4b729b99193a921c5f6965e48815261
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="profiling-and-windows-vista-security"></a>Profilage et sécurité Windows Vista
Selon les paramètres d’autorisation d’accès utilisateur de [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)] mis à disposition par l’administrateur d’un ordinateur, un utilisateur individuel peut disposer de l’autorisation de sécurité pour profiler un processus sur cet ordinateur. Les exemples suivants montrent les différences possibles entre les utilisateurs :  
  
-   Certains utilisateurs peuvent accéder à des fonctionnalités de profilage avancées quand l’administrateur a défini le démarrage du pilote et du service.  
  
-   Les utilisateurs de domaine peuvent accéder seulement au profilage d’échantillon.  
  
-   Certains utilisateurs peuvent refuser l’accès au profilage à tous les autres utilisateurs.  
  
 Pour plus d’informations, consultez les options d’administration dans [VSPerfCmd](../profiling/vsperfcmd.md).  
  
## <a name="cross-session-profiling"></a>Profilage intersession  
 Le *profilage intersession* est la capacité à profiler un processus qui s’exécute dans une autre session ouverte. Par exemple, la plupart des services s’exécutent dans la session 0, et les utilisateurs ne peuvent pas s’exécuter directement dans la session 0. À l’aide du bouton **Attacher au processus** de la barre d’outils de l’Explorateur de performances ou de l’option /attach de l’outil en ligne de commande VSPerfCmd, vous pouvez profiler la plupart des processus dans plusieurs sessions ouvertes.  
  
 Pour consulter la liste des processus disponibles, définissez les options de visibilité du profilage interprocessus. Ces options sont disponibles dans la fenêtre **Attacher au processus** qui s’affiche quand vous cliquez sur **Attacher au processus** :  
  
-   **Afficher les processus de tous les utilisateurs**  
  
     Quand cette option n’est pas sélectionnée, la liste affiche uniquement les processus détenus par l’utilisateur actuel. Quand **elle** est sélectionnée, la liste affiche les processus de tous les utilisateurs.  
  
-   **Afficher les processus de toutes les sessions**  
  
     Quand cette option n’est pas sélectionnée, la liste affiche les processus de la session active. Quand elle est sélectionnée, la liste affiche les processus de toutes les sessions.  
  
## <a name="see-also"></a>Voir aussi  
 [Vues d’ensemble](../profiling/overviews-performance-tools.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Guide pratique pour attacher un processus à un processus en cours d’exécution](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)