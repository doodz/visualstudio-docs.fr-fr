---
title: Outils de profilage dans Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.diagnosticshub.overview
ms.assetid: 0fb6cd5d-e16a-4526-84a5-19e63c625bc5
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 0d129b4820944f5717c63243cb8550bc4fed3385
ms.openlocfilehash: 380b65540d8f5c6ea6d8a8adf1f3c5575f5dd9dc
ms.lasthandoff: 03/20/2017

---
# <a name="profiling-tools"></a>Outils de profilage
Les outils de profilage et de diagnostic vous aident à diagnostiquer l’utilisation de la mémoire et du processeur et d’autres problèmes au niveau de l’application. Grâce à ces outils, vous pouvez accumuler des données (par exemple, des valeurs de variables, des appels de fonctions et des événements) pendant que vous exécutez votre application dans le débogueur. Vous pouvez examiner l’état de votre application à différents stades au cours de l’exécution de votre code.  
  
 Vous trouverez au bas de l’article un récapitulatif des outils disponibles pour le type de votre projet (par exemple, application de bureau, UWP, ASP.NET).  
  
 Vous pouvez accéder aux outils de profilage en sélectionnant **Déboguer / Windows / Afficher les outils de diagnostic** pour utiliser les outils durant votre session de débogage, ou vous pouvez effectuer une analyse « post-mortem » en adoptant d’autres approches.  Pour plus d’informations sur les différentes approches, consultez [Exécution des outils de profilage avec ou sans le débogueur](../profiling/running-profiling-tools-with-or-without-the-debugger.md) .
  
 ![DebugDiagnosticsToolsMenu](../profiling/media/debugdiagnosticstoolsmenu.png "DebugDiagnosticsToolsMenu")
  
 Pour en savoir plus sur les nouvelles fonctionnalités de cette version, consultez [Nouveautés des outils de profilage](../profiling/what-s-new-in-profiling-tools.md).
  
 Les sections suivantes décrivent les différents outils d’analyse des performances disponibles dans Visual Studio.
  
## <a name="memory-usage"></a>Utilisation de la mémoire  
 ![DiagMemorySmall](../profiling/media/diagmemorysmall.png "DiagMemorySmall")  
  
 Identifiez les fuites de mémoire et les utilisations inefficaces de la mémoire pendant le débogage à l’aide de l’outil **Utilisation de la mémoire** . L’outil vous permet de prendre des captures instantanées du tas de mémoire managé et natif. Vous pouvez utiliser cet outil avec les applications de bureau, les applications universelles Windows et les applications ASP.NET. L’outil **Utilisation de la mémoire** peut être exécuté à partir de la fenêtre **Outils de diagnostic** pendant le débogage (**Déboguer / Windows / Afficher les outils de diagnostic**) ou en dehors du débogueur (**Déboguer / Profileur de performances...**). Pour plus d’informations, consultez [Utilisation de la mémoire](../profiling/memory-usage.md) et [Utilisation de la mémoire sans débogage](../profiling/Memory-Usage-without-Debugging2.md) .  
  
## <a name="cpu-usage"></a>Utilisation de l'UC  
 ![DiagCPUSmall](../profiling/media/diagcpusmall.png "DiagCPUSmall")  
  
 L'outil **Utilisation du processeur** vous montre où le processeur consacre son temps à exécuter le code C++, C#/VB et JavaScript.  Vous pouvez utiliser cet outil avec les applications de bureau et les applications universelles Windows, mais aussi avec les applications ASP.NET et Azure App Services. L’outil **Utilisation de l’UC** peut être exécuté à partir de la fenêtre **Outils de diagnostic** pendant le débogage (**Déboguer / Windows / Afficher les outils de diagnostic**) ou en dehors du débogueur (**Déboguer / Profileur de performances...**). Pour plus d’informations, consultez le [Guide du débutant du profilage des performances](../profiling/beginners-guide-to-performance-profiling.md) et [Utilisation de l’UC](../profiling/cpu-usage.md).
  
## <a name="gpu-usage"></a>Utilisation du GPU  
 ![DiagGPUUsage](../profiling/media/diaggpuusage.png "DiagGPUUsage")  
  
 Utilisez l’outil [GPU Usage](../debugger/gpu-usage.md) pour mieux comprendre l’utilisation générale du matériel par votre application Direct3D. Vous pouvez utiliser cet outil avec les applications de bureau et les applications universelles Windows, mais pas avec les applications ASP.NET. Vous pouvez exécuter l’outil **Utilisation du GPU** en dehors du débogueur (**Déboguer / Profileur de performances...**).  
  
## <a name="application-timeline"></a>Chronologie de l'application  
 ![DiagAppTimeline](../profiling/media/diagapptimeline.png "DiagAppTimeline")  
  
 L’outil [Chronologie de l’application](../profiling/application-timeline.md) vous aide à améliorer les performances des applications XAML en offrant une vue détaillée de leur consommation de ressources. Vous pouvez utiliser **Chronologie de l’application** avec les applications de bureau et les applications universelles Windows, mais pas avec les applications ASP.NET. L’outil **Chronologie de l’application** peut être exécuté en dehors du débogueur (**Déboguer / Profileur de performances...**).
  
## <a name="perftips"></a>Conseils sur les performances  
 ![DiagPerfTips](../profiling/media/diagperftips.png "DiagPerfTips")  
  
 Quand le débogueur arrête l'exécution à un point d'arrêt ou lors de l'exécution pas à pas, le temps qui s'écoule entre l'arrêt et le point d'arrêt précédent apparaît sous la forme d'un conseil dans la fenêtre de l'éditeur. Ces [PerfTips](../profiling/perftips.md) vous permettent de surveiller et d’analyser les performances de votre application pendant le débogage. Vous pouvez afficher les **Conseils sur les performances** dans les applications de bureau, les applications universelles Windows et les applications ASP.NET.

## <a name="performance-explorer"></a>Explorateur de performances  
 ![PerfTools](../profiling/media/perftools.png "PerfTools")  
  
 L’ **Explorateur de performances** (**Déboguer / Profileur / Explorateur de performances**) vous permet d’utiliser différents outils, dont **Échantillonnage de l’UC**,  **Instrumentation**, **Allocation de mémoire .NET**et **Conflit de ressources**. Vous pouvez utiliser les outils Explorateur de performances avec les applications de bureau et les applications ASP.NET, mais pas avec les applications universelles Windows. Pour plus d’informations, consultez [Explorateur de performances](../profiling/performance-explorer.md).

 > [!NOTE]
 > Utilisez les outils de diagnostics tels qu’Utilisation de la mémoire et Utilisation de l’UC plutôt que l’Explorateur de performances (qui est désormais un outil hérité), sauf si vous souhaitez effectuer une tâche spécialisée telle que l’instrumentation.
  
## <a name="javascript-memory"></a>Mémoire JavaScript  
 ![DiagJSMemory](../profiling/media/diagjsmemory.png "DiagJSMemory")  
  
 L’outil [Mémoire JavaScript](../profiling/javascript-memory.md) vous permet de rechercher les fuites de mémoire et l’utilisation inefficace de la mémoire dans vos applications. L’outil vous permet de prendre des instantanés du tas JavaScript. Vous pouvez utiliser cet outil avec les applications HTML universelles Windows. Vous pouvez exécuter l’outil **Mémoire JavaScript** en dehors du débogueur (**Déboguer / Profileur de performances...**).  
  
## <a name="html-ui-responsiveness"></a>Réactivité de l'interface utilisateur HTML  
 ![DiagHTMLResp](../profiling/media/diaghtmlresp.png "DiagHTMLResp")  
  
 L’outil [Réactivité de l’interface utilisateur HTML](../profiling/html-ui-responsiveness.md) vous aide à isoler les problèmes de performances dans vos applications, comme le manque de réactivité, les lenteurs de chargement et les mises à jour visuelles qui sont moins fréquentes que prévu. Vous pouvez utiliser cet outil avec les applications HTML universelles Windows. Vous pouvez exécuter l’outil **Réactivité de l’interface utilisateur HTML** en dehors du débogueur (**Déboguer / Profileur de performances...**).  
  
## <a name="intellitrace"></a>IntelliTrace  
 ![DiagIntelliTrace](../profiling/media/diagintellitrace.png "DiagIntelliTrace")  
  
 [IntelliTrace](../debugger/intellitrace.md) vous permet d’inscrire des événements spécifiques, d’examiner les données dans la fenêtre **Variables locales** pendant les événements de débogueur et les appels de fonctions, ainsi que les erreurs de débogage difficiles à reproduire.  IntelliTrace est avant tout un outil de débogage, mais il procure aussi des informations qui peuvent être exploitées pour effectuer des recherches sur les performances. Vous pouvez utiliser cet outil dans Visual Studio Enterprise uniquement, avec les applications de bureau, les applications universelles Windows et les applications C# ASP.NET. Vous pouvez trouver IntelliTrace dans la fenêtre **Outils de diagnostic** pendant le débogage (**Déboguer / Windows / Afficher les outils de diagnostic**).  
  
## <a name="profiling-in-production"></a>Profilage en production  
 La méthode recommandée en matière de profilage en production consiste à profiler à partir de la [ligne de commande en utilisant vsperf.exe](../profiling/using-the-profiling-tools-from-the-command-line.md) pour collecter un profil d’UC. Pour bénéficier d’une prise en charge du profilage à distance dans Azure App Service, vous pouvez profiler via l’ [Explorateur de serveurs ou le portail Kudu](https://azure.microsoft.com/en-us/blog/remote-profiling-support-in-azure-app-service/).  
  
## <a name="which-tool-should-i-use"></a>Quel outil utiliser ?  
 Voici un tableau qui recense les différents outils proposés par Visual Studio, ainsi que les différents types de projet avec lesquels vous pouvez les utiliser :  
  
|Outil d’analyse des performances|Bureau Windows|Universel Windows/Store|ASP.NET/ASP.NET Core|  
|----------------------|---------------------|------------------------------|-------------|  
|[Utilisation de la mémoire](../profiling/memory-usage.md)|oui|oui|oui|  
|[Utilisation de l’UC](../profiling/cpu-usage.md)|oui|oui|oui|  
|[Utilisation du GPU](../debugger/gpu-usage.md)|oui|oui|non|  
|[Chronologie de l’application](../profiling/application-timeline.md)|oui|oui|non|  
|[PerfTips](../profiling/perftips.md)|oui|oui pour XAML, non pour HTML|oui|  
|[Explorateur de performances](../profiling/performance-explorer.md)|oui|non|oui (non pour ASP.NET Core)|  
|[IntelliTrace](../debugger/intellitrace.md)|.NET Enterprise uniquement|.NET Enterprise uniquement|.NET Enterprise uniquement|
|[Utilisation du réseau](../profiling/network-usage.md)|non|oui|non| 
|[Réactivité de l’interface utilisateur HTML](../profiling/html-ui-responsiveness.md)|non|oui pour HTML, non pour XAML|non|  
|[Mémoire JavaScript](../profiling/javascript-memory.md)|non|oui pour HTML, non pour XAML|non|  
  
## <a name="see-also"></a>Voir aussi  
 [IDE Visual Studio](../ide/visual-studio-ide.md)