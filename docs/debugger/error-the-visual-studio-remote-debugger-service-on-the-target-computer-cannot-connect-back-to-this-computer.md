---
title: "Erreur : Le service débogueur distant Visual Studio sur l’ordinateur cible ne peut pas se connecter à cet ordinateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.service_access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 89ecf99d-66bf-4da0-a840-aa95b0be1702
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4f1707f7956557cb8ce764f66431dbf963dcfb79
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer"></a>Erreur : Le service Débogueur distant Visual Studio sur l'ordinateur cible ne peut pas se reconnecter à cet ordinateur
Cette erreur signifie que le service Débogueur distant Visual Studio s'exécute sous un compte d'utilisateur qui ne peut pas être authentifié lorsqu'il se connecte à l'ordinateur à partir duquel vous déboguez.  
  
 Le tableau suivant répertorie les comptes autorisés à accéder à l'ordinateur:  
  
|||||  
|-|-|-|-|  
||Compte LocalSystem|Compte de domaine|Comptes locaux avec les mêmes nom d'utilisateur et mot de passe sur les deux ordinateurs|  
|Deux ordinateurs sur le même domaine|Oui|Oui|Oui|  
|Deux ordinateurs sur des domaines qui ont un niveau de confiance bidirectionnel|Non|Non|Oui|  
|Un ordinateur, ou les deux, dans un groupe de travail|Non|Non|Oui|  
|Ordinateurs sur des domaines différents|Non|Non|Oui|  
  
 De plus :  
  
-   Le compte sous lequel vous exécutez le service Débogueur distant Visual Studio doit être un administrateur sur l'ordinateur distant afin qu'il puisse déboguer tout processus.  
  
-   Le compte doit également être accordé le `Log on as a service` privilège sur l’ordinateur distant qui utilise le **stratégie de sécurité locale** outil d’administration.  
  
-   Si vous utilisez un compte local pour accéder à l'ordinateur, vous devez exécuter le service Débogueur distant Visual Studio sous un compte local.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Assurez-vous que le service Débogueur distant Visual Studio est correctement installé sur l'ordinateur distant. Pour plus d’informations, consultez [débogage distant](../debugger/remote-debugging.md).  
  
2.  Exécutez le service Débogueur distant sous un compte qui peut accéder à l'ordinateur hôte du débogueur, comme indiqué dans le tableau précédent.  
  
### <a name="to-add-log-on-as-a-service-privilege"></a>Pour ajouter le privilège « Ouvrir une session en tant que service »  
  
1.  Sur le **Démarrer** menu, choisissez **le panneau de configuration**.  
  
2.  Dans le panneau de configuration, choisissez **affichage classique**, si nécessaire.  
  
3.  Double-cliquez sur **Outils d'administration**.  
  
4.  Dans la fenêtre Outils d’administration, double-cliquez sur **stratégie de sécurité locale**.  
  
5.  Dans le **paramètres de sécurité locaux** fenêtre, développez le **stratégies locales** dossier.  
  
6.  Cliquez sur **attribution des droits utilisateur**.  
  
7.  Dans le **stratégie** colonne, double-cliquez sur **ouvrir une session en tant que service** pour afficher les affectations de stratégie de groupe locales dans le **ouvrir une session en tant que service** boîte de dialogue.  
  
8.  Pour ajouter de nouveaux utilisateurs, cliquez sur le **ajouter un utilisateur ou groupe** bouton.  
  
9. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **OK**.  
  
### <a name="to-work-around-this-error"></a>Pour contourner cette erreur  
  
-   Exécutez le Remote Debugging Monitor comme une application au lieu d'un service.  
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs de débogage distant et dépannage](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Débogage à distance](../debugger/remote-debugging.md)