---
title: "Comment&#160;: instrumenter un service natif et collecter des donn&#233;es de temporisation d&#233;taill&#233;es en utilisant la ligne de commande du profileur | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dfe58b39-63f8-4a87-ab3a-2b5b14faa8d0
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Comment&#160;: instrumenter un service natif et collecter des donn&#233;es de temporisation d&#233;taill&#233;es en utilisant la ligne de commande du profileur
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Cette rubrique explique comment utiliser les outils en ligne de commande des outils de profilage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pour instrumenter un service \(C\/C\+\+\) natif et collecter des données de temporisation détaillées.  
  
> [!NOTE]
>  Vous ne pouvez pas profiler un service avec la méthode d'instrumentation si ce service ne peut pas être redémarré après le démarrage de l'ordinateur, tel qu'un service qui démarre uniquement au démarrage du système d'exploitation.  
>   
>  Les outils en ligne de commande des outils de profilage se trouvent dans le sous\-répertoire \\Team Tools\\Performance Tools du répertoire d'installation de [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] s  Sur les ordinateurs 64 bits, les versions 64 bits et 32 bits de ces outils sont disponibles.  Pour utiliser les outils en ligne de commande du profileur, vous devez ajouter le chemin d'accès des outils à la variable d'environnement PATH de la fenêtre d'invite de commandes ou l'ajouter à la commande elle\-même.  Pour plus d'informations, consultez [Spécification du chemin d'accès aux outils en ligne de commande](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Pour collecter les données de temporisation détaillées d'un service natif à l'aide de la méthode d'instrumentation, utilisez l'outil [VSInstr.exe](../profiling/vsinstr.md) pour générer une version instrumentée du composant.  Remplacez ensuite la version non instrumentée du service par la version instrumentée, en vous assurant que le service est configuré pour démarrer manuellement.  Vous démarrez alors le profileur.  
  
 Lorsque le service est démarré, les données de temporisation sont collectées automatiquement dans un fichier de données.  Vous pouvez suspendre et reprendre la collecte de données pendant la session de profilage.  
  
 Pour terminer une session de profilage, arrêtez le service, puis arrêtez explicitement le profileur.  
  
## Démarrage de l'application avec le profileur  
  
#### Pour commencer le profilage d'un service natif  
  
1.  Ouvrez une fenêtre d'invite de commandes.  
  
2.  Utilisez l'outil **VSInstr** pour générer une version instrumentée du binaire de service.  
  
3.  Remplacez le binaire d'origine par la version instrumentée.  Dans le Gestionnaire de contrôle des services Microsoft, assurez\-vous que le service Type de démarrage a la valeur Manuel.  
  
4.  Démarrez le profileur.  Type :  
  
     **VSPerfCmd** [\/start](../profiling/start.md)**:trace** [\/output](../profiling/output.md)**:**`OutputFile` \[`Options`\]  
  
    -   L'option **\/start:trace** initialise le profileur.  
  
    -   L'option **\/output:**`OutputFile` est requise avec **\/start**.  `OutputFile` spécifie le nom et l'emplacement du fichier de données de profilage \(.vsp\).  
  
     Vous pouvez utiliser n'importe laquelle des options suivantes avec l'option **\/start:trace**.  
  
    > [!NOTE]
    >  Les options **\/user** et **\/crosssession** sont généralement requises pour les applications ASP.NET.  
  
    |Option|Description|  
    |------------|-----------------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|Spécifie le domaine et le nom d'utilisateur du compte qui possède le processus de travail ASP.NET.  Cette option est requise si le processus s'exécute en tant qu'un utilisateur autre que l'utilisateur connecté.  Le propriétaire du processus est répertorié dans la colonne Nom d'utilisateur sous l'onglet Processus du Gestionnaire des tâches de Windows.|  
    |[\/crosssession](../profiling/crosssession.md)|Active le profilage de processus dans d'autres ouvertures de session.  Cette option est requise si l'application ASP.NET s'exécute dans une session différente.  L'identificateur de session est répertorié dans la colonne Identificateur de session sous l'onglet Processus du Gestionnaire des tâches de Windows.  **\/CS** peut être spécifié en tant qu'abréviation de **\/crosssession**.|  
    |[\/waitstart](../profiling/waitstart.md)\[**:**`Interval`\]|Spécifie le nombre de secondes d'attente lors de l'initialisation du profileur avant qu'une erreur ne soit retournée.  Si `Interval` n'est pas spécifié, le profileur attend indéfiniment.  Par défaut, **\/start** est immédiatement retourné.|  
    |[\/globaloff](../profiling/globalon-and-globaloff.md)|Pour démarrer le profileur avec la collecte de données en pause, ajoutez l'option **\/globaloff** à la ligne de commande **\/start**.  Utilisez **\/globalon** pour reprendre le profilage.|  
    |[\/counter](../profiling/counter.md) **:** `Config`|Collecte des informations du compteur de performance de processeur spécifié dans Config.  Des informations de compteur sont ajoutées aux données collectées à chaque événement de profilage.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Spécifie un compteur de performance Windows à collecter au cours du profilage.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|À n'utiliser qu'avec **\/wincounter**.  Spécifie le nombre de millisecondes entre les événements de collecte du compteur de performance Windows.  La valeur par défaut est de 500 ms.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|Spécifie un événement ETW \(Event Tracing for Windows\) à collecter au cours du profilage.  Les événements ETW sont collectés dans un fichier séparé \(.etl\).|  
  
5.  Démarrez le service à partir du Gestionnaire de contrôle des services.  
  
## Contrôle de la collecte de données  
 Lorsque le service s'exécute, vous pouvez utiliser les options **VSPerfCmd.exe** pour démarrer et arrêter l'écriture de données dans le fichier de données du profileur.  Le contrôle de la collecte de données vous permet de collecter des données pour une partie spécifique de l'exécution du programme, notamment le démarrage ou l'arrêt du service.  
  
#### Pour démarrer et arrêter la collecte de données  
  
-   Les paires suivantes d'options **VSPerfCmd** démarrent et arrêtent la collecte de données.  Spécifiez chaque option sur une ligne de commande séparée.  Vous pouvez activer et désactiver la collecte de données à plusieurs reprises.  
  
    |Option|Description|  
    |------------|-----------------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|Démarre \(**\/globalon**\) ou arrête \(**\/globaloff**\) la collecte de données pour tous les processus.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID` [\/processoff](../profiling/processon-and-processoff.md)**:**`PID`|Démarre \(**\/processon**\) ou arrête \(**\/processoff**\) la collecte de données pour le processus spécifié par l'ID de processus \(`PID`\).|  
    |[\/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [\/threadoff](../profiling/threadon-and-threadoff.md)**:**`TID`|Démarre \(**\/threadon**\) ou arrête \(**\/threadoff**\) la collecte de données pour le thread spécifié par l'ID de thread \(`TID`\).|  
  
## Fin de la session de profilage  
 Pour terminer une session de profilage, arrêtez le service qui exécute le composant instrumenté, puis appelez l'option **VSPerfCmd**[\/shutdown](../profiling/shutdown.md) pour arrêter le profileur et fermer le fichier de données de profilage.  
  
#### Pour terminer une session de profilage  
  
1.  Arrêtez le service à partir du Gestionnaire de contrôle des services.  
  
2.  Arrêtez le profileur.  Type :  
  
     **VSPerfCmd \/shutdown**  
  
3.  Remplacez le module instrumenté par le module d'origine.  Si nécessaire, reconfigurez le type de démarrage du service.  
  
## Voir aussi  
 [Profilage de services](../profiling/command-line-profiling-of-services.md)   
 [Vues de données de la méthode d'instrumentation](../profiling/instrumentation-method-data-views.md)