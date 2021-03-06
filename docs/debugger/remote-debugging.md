---
title: "Débogage distant dans Visual Studio | Documents Microsoft"
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: hero-article
f1_keywords: vs.debug.remote.overview
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords: remote debugging, setup
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
caps.latest.revision: "65"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d945c28e7fe703c80776a5f1ff124ab6e0a8bf9
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2017
---
# <a name="remote-debugging"></a>Remote Debugging
Vous pouvez déboguer une application Visual Studio qui a été déployée sur un autre ordinateur. Pour ce faire, utilisez le débogueur distant Visual Studio.

Pour obtenir des instructions détaillées sur le débogage distant, consultez les rubriques suivantes.

|Scénario|Lien|
|-|-|-|
|ASP.NET|[Débogage ASP.NET Core à distance](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md) ou [ASP.NET du débogage distant](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|C# ou Visual Basic|[Débogage d’un projet c# ou Visual Basic à distance](remote-debugging-csharp.md)|
|C++|[Débogage à distance d’un projet C++](remote-debugging-cpp.md)|
|Applications Windows universelles (UWP)|[Déboguer le package d'application installé](debug-installed-app-package.md)|
|Azure|[ASP.NET de débogage distant sur Azure](remote-debugging-azure.md)|
|Azure Service Fabric|[Déboguer une application de Service Fabric distante](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application).|

Si vous simplement télécharger et installer le débogueur distant et que vous n’avez pas besoin des instructions supplémentaires pour votre scénario, suivez les étapes décrites dans cet article.
  
## <a name="download-and-install-the-remote-tools"></a>Télécharger et installer les outils de contrôle à distance  

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

### <a name="fileshare_msvsmon"></a>(Facultatif) Pour exécuter le débogueur distant à partir d’un partage de fichiers

Vous pouvez trouver le débogueur distant (**msvsmon.exe**) sur un ordinateur avec Visual Studio Community, Professional ou Enterprise déjà installé. Pour certains scénarios, le moyen le plus simple pour configurer le débogage à distance doit exécuter le débogueur distant (msvsmon.exe) à partir d’un partage de fichiers. Pour connaître les limitations d’utilisation, consultez la page d’aide du débogueur distant (**aide > utilisation** dans le débogueur distant).

1. Rechercher **msvsmon.exe** dans le répertoire correspondant à votre version de Visual Studio. Pour Visual Studio Enterprise 2017 :

      **Programme fichiers (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x86\msvsmon.exe**
      
      **Programme fichiers (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x64\msvsmon.exe**

2. Partage les **débogueur distant** dossier sur l’ordinateur Visual Studio.

3. Sur l’ordinateur distant, exécutez **msvsmon.exe**. Suivez les [instructions d’installation](#bkmk_setup).

> [!TIP] 
> Pour l’installation de la ligne de commande et référence de ligne de commande, consultez la page d’aide **msvsmon.exe** en tapant ``msvsmon.exe /?`` dans la ligne de commande sur l’ordinateur avec Visual Studio est installé (ou accédez à **aide > utilisation**dans le débogueur distant).
  
## <a name="requirements_msvsmon"></a> Spécifications

[!INCLUDE [remote-debugger-requirements](../debugger/includes/remote-debugger-requirements.md)]
  
## <a name="set-up-the-remote-debugger"></a>Configurer le débogueur distant  

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

### <a name="configure_msvsmon"></a>Configurer le débogueur distant  
Vous pouvez modifier certains aspects de la configuration du débogueur distant après l’avoir démarré pour la première fois.
  
-   Si vous avez besoin ajouter des autorisations pour d’autres utilisateurs pour se connecter au débogueur distant, choisissez **Outils > autorisations**. Vous devez disposer de privilèges d’administrateur pour accorder ou refuser des autorisations.

     > [!IMPORTANT] 
     > Vous pouvez exécuter le débogueur distant sous un compte d’utilisateur qui est différent du compte d’utilisateur que vous utilisez sur l’ordinateur Visual Studio, mais vous devez ajouter le compte d’utilisateur différent pour les autorisations du débogueur distant. 

     Vous pouvez également démarrer le débogueur distant à partir de la ligne de commande avec le **/ autoriser \<nom d’utilisateur >** paramètre : **msvsmon /Allow \< username@computer>**.
  
-   Si vous avez besoin de modifier le mode d’authentification ou le numéro de port ou spécifier une valeur de délai d’attente pour les outils à distance : choisissez **Outils > Options**.  
  
     Pour obtenir la liste des numéros de port utilisés par défaut, consultez [affectations de Port du débogueur distant](../debugger/remote-debugger-port-assignments.md).  
  
     > [!WARNING]
     >  Vous pouvez choisir d’exécuter les outils de contrôle à distance en mode Aucune authentification, mais ce mode est fortement déconseillé. Il n’existe aucune sécurité du réseau lorsque vous lancez l’exécution dans ce mode. Sélectionnez le mode Aucune authentification uniquement si vous êtes sûr que le réseau n’est pas exposé à des failles de sécurité liées à des programmes malveillants ou du trafic dangereux.

##  <a name="bkmk_configureService"></a>(Facultatif) Configurer le débogueur distant en tant que service
Pour déboguer dans ASP.NET et autres environnements de serveurs, vous devez exécuter le débogueur distant en tant qu’administrateur ou, si vous voulez qu’il est toujours en cours d’exécution, exécutez le débogueur distant en tant que service.
  
 Si vous souhaitez configurer le débogueur distant en tant que service, procédez comme suit.  
  
1.  Recherchez l’ **Assistant Configuration Remote Debugger** (rdbgwiz.exe). (C’est une application distincte du débogueur distant). Il est disponible uniquement quand vous installez les outils de contrôle à distance. Il n’est pas installé avec Visual Studio.  
  
2.  Démarrez l’Assistant Configuration. Quand la première page s’affiche, cliquez sur **Suivant**.  
  
3.  Cochez la case **Exécuter le débogueur distant Visual Studio 2015 en tant que service** .  
  
4.  Ajoutez le nom du compte d’utilisateur et le mot de passe.  
  
     Il se pouvez que vous deviez ajouter le **ouvrir une session en tant que service** droite à ce compte d’utilisateur (rechercher **stratégie de sécurité locale** (secpol.msc) dans le **Démarrer** page ou la fenêtre (ou type  **secpol.msc** à une invite de commandes). Quand la fenêtre s’affiche, double-cliquez sur **Attribution des droits utilisateur**, puis recherchez **Ouvrir une session en tant que service** dans le volet droit. Double-cliquez dessus. Ajoutez le compte d’utilisateur pour le **propriétés** fenêtre et cliquez sur **OK**). Cliquez sur **Suivant**.  
  
5.  Sélectionnez le type de réseau avec lesquel vous voulez que les outils de contrôle à distance communiquent. Au moins un type de réseau doit être sélectionné. Si les ordinateurs sont connectés à un domaine, vous devez choisir le premier élément. Si les ordinateurs sont connectés à un groupe de travail ou un groupe résidentiel, vous devez choisir le deuxième ou troisième élément. Cliquez sur **Suivant**.  
  
6.  Si le service peut être démarré, le message suivant s’affiche : **L’Assistant Configuration Visual Studio Remote Debugger est terminé**. Si le service ne peut pas être démarré, le message suivant s’affiche : **Échec de l’Assistant Configuration Débogueur distant Visual Studio**. La page fournit également des conseils à suivre pour faire démarrer le service.  
  
7.  Cliquez sur **Terminer**.  
  
 À ce stade, le débogueur distant s’exécute en tant que service. Vous pouvez le vérifier en accédant à **le panneau de configuration > Services** et en recherchant **débogueur distant Visual Studio 2015**.  
  
 Vous pouvez arrêter et démarrer le service débogueur distant à partir de **le panneau de configuration > Services**.

## <a name="set-up-debugging-with-remote-symbols"></a>Configurer le débogage avec des symboles distants 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]
  
## <a name="see-also"></a>Voir aussi  
 [Visite guidée des fonctionnalités du débogueur](../debugger/debugger-feature-tour.md)   
 [Configurer le pare-feu Windows pour le débogage distant](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [Affectations de Port du débogueur distant](../debugger/remote-debugger-port-assignments.md)   
 [Débogage ASP.NET Core sur un ordinateur distant IIS distant](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [Erreurs et résolution des problèmes du débogage distant](../debugger/remote-debugging-errors-and-troubleshooting.md)
