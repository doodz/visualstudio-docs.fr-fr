---
title: Application Lifecycle Management (ALM) avec les applications Xamarin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff978cc2-5a25-46d6-921b-e51adaa65992
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 41fe8afba19939dfbbbd5c055f5ebd53e9fc2e04
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="application-lifecycle-management-alm-with-xamarin-apps"></a>Application Lifecycle Management (ALM) avec les applications Xamarin
Xamarin vous permet de générer des applications mobiles multiplateformes ciblant Android, iOS et Windows à l’aide de C#, .NET et Visual Studio. Xamarin autorise le partage d’une grande partie du code entre les plateformes. Seul un petit pourcentage du code doit être spécifique à chaque plateforme. Pour plus d’informations sur Xamarin, consultez [Visual Studio et Xamarin](../cross-platform/visual-studio-and-xamarin.md).  
  
 Le développement d'applications pour des plateformes modernes implique de nombreuses activités qui vont bien au-delà de la simple écriture de code. Ces activités, appelées DevOps (développement + opérations), couvrent le cycle de vie complet de l’application et incluent la planification et le suivi du travail, la conception et l’implémentation du code, la gestion d’un dépôt de code source, l’exécution des builds, la gestion des intégrations continues et des déploiements continus, les tests (notamment les tests unitaires et les tests d’IU), l’exécution de différentes formes de diagnostics dans les environnements de développement et de production, ainsi que la surveillance en temps réel des performances des applications et des comportements des utilisateurs par le biais de la télémétrie et l’analyse.  
  
 Visual Studio, Visual Studio Team Services et Team Foundation Server fournissent de nombreuses fonctionnalités DevOps, également appelées fonctionnalités Application Lifecycle Management (ALM). Bon nombre d'entre elles sont entièrement applicables aux projets multiplateformes.  
  
 Cela est particulièrement vrai en ce qui concerne les applications Xamarin, car elles font appel à du code C# et .NET, sur lequel certains outils ALM sont basés. D’autres outils nécessitent une intégration étroite avec les environnements de build et d’exécution. Étant donné que les applications Xamarin s'exécutent sur des plateformes non-Windows et qu'elles utilisent l'implémentation Mono de .NET, Xamarin fournit des outils spécialisés pour répondre à certains besoins.  
  
 Les tableaux ci-dessous identifient les fonctionnalités ALM de Visual Studio qui donnent de bons résultats avec un projet Xamarin, et celles qui présentent des limites. Pour plus d'informations sur les fonctionnalités, cliquez sur les liens correspondants.  
  
## <a name="agile-tools"></a>Outils agiles  
 Lien de référence : **[Travail](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503)** (avec Visual Studio Team Services ou TFS, notamment Team Explorer Everywhere)  
  
 Commentaire général : toutes les fonctionnalités de planification et de suivi sont indépendantes du type de projet et des langages de codage.  
  
|Fonctionnalité|Prise en charge par Xamarin|Commentaires supplémentaires|  
|-------------|----------------------------|-------------------------|  
|Gérer les backlogs et les sprints|Oui||  
|Suivi du travail|Oui||  
|Collaboration dans la salle d'équipe|Oui||  
|Tableaux kanban|Oui||  
|Créer des rapports sur la progression et la visualiser|Oui||  
  
## <a name="modeling"></a>Modélisation  
 Lien de référence : **[Analyse et modélisation de l’architecture](../modeling/analyze-and-model-your-architecture.md)**  
  
 Les fonctionnalités de conception sont indépendantes du langage de codage ou fonctionnent avec les langages .NET tels que C#. Consultez [Rôles de l’architecture et des diagrammes de modélisation dans le développement de logiciels](../modeling/scenario-change-your-design-using-visualization-and-modeling.md#ModelingDiagramsTools) pour connaître les aspects liés au code.  
  
|Fonctionnalité|Prise en charge par Xamarin|Commentaires supplémentaires|  
|-------------|----------------------------|-------------------------|  
|Diagrammes de séquence|Oui||  
|Graphiques de dépendance|Oui||  
|Hiérarchie d'appels|Oui||  
|Concepteur de classes|Oui||  
|Navigateur de l'architecture|Oui||  
|Diagrammes UML (cas d'usage, activité, classe, composant, séquence et DSL)|Oui||  
|Diagrammes de couche|Oui||  
|Validation de couche|Oui||  
  
## <a name="code"></a>Code  
  
|Fonctionnalité|Prise en charge par Xamarin|Commentaires supplémentaires|  
|-------------|----------------------------|-------------------------|  
|[Utiliser Team Foundation Version Control](http://msdn.microsoft.com/Library/1d629052-c65d-4c5d-81eb-eaa4413fe285) ou Visual Studio Team Services|Oui||  
|[Bien démarrer avec Git dans Team Services](http://msdn.microsoft.com/Library/32f46ecd-1b03-4ef0-a9c4-8a120da2b03f)|Oui||  
|[Améliorer la qualité du code](/visualstudio/test/improve-code-quality)|Oui||  
|[Rechercher les modifications de code et d’autres historiques](../ide/find-code-changes-and-other-history-with-codelens.md)|Oui|Sauf au-delà des limites spécifiques de la plateforme où l’implémentation n’est résolue qu’au moment de l’exécution.|  
|[Utiliser des cartes de code pour déboguer vos applications](../modeling/use-code-maps-to-debug-your-applications.md)|Oui||  
  
## <a name="build"></a>Build  
 Lien de référence : **[Build](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)**  
  
|Fonctionnalité|Prise en charge par Xamarin|Commentaires supplémentaires|  
|-------------|----------------------------|-------------------------|  
|Serveur TFS local|Oui|Xamarin doit être installé sur les machines de build. Celles-ci peuvent être liées à un ordinateur OSX afin de générer des applications pour iOS. Consultez [Configuration de TFS pour Xamarin](http://developer.xamarin.com/guides/cross-platform/ci/configuring_tfs/) (site web Xamarin).|  
|Serveur de builds local lié à Visual Studio Team Services|Oui|Consultez la rubrique [Serveur de builds](http://msdn.microsoft.com/Library/2d258a0a-f178-4e93-9da1-eba61151af3c) pour obtenir des instructions.|  
|Service de contrôleur hébergé de Visual Studio Team Services|Oui|Consultez [Générez votre application Xamarin](https://www.visualstudio.com/en-us/docs/build/apps/mobile/xamarin).|  
|Définitions de builds avec des pré-scripts et des post-scripts|Oui||  
|Intégration continue, y compris les archivages contrôlés|Oui|Archivages contrôlés pour TFVC uniquement si Git utilise un modèle de requête d'extraction plutôt que des archivages.|  
  
## <a name="testing"></a>Test  
 Lien de référence : **[Test de l’application](/devops-test-docs/test/test-apps-early-and-often)**  
  
|Fonctionnalité|Prise en charge par Xamarin|Commentaires supplémentaires|  
|-------------|----------------------------|-------------------------|  
|Planification de tests, création de cas de test et organisation de suites de tests|Oui||  
|Test manuel|Oui||  
|Gestionnaire de tests (enregistrer et rejouer des tests)|Oui|Appareils Windows et émulateurs Android uniquement à partir de Visual Studio. L’enregistrement est possible pour tous les appareils avec [Xamarin Test Recorder](https://www.xamarin.com/test-cloud/recorder).|  
|Couverture du code|N/A||  
|[Tests unitaires sur votre code](../test/unit-test-your-code.md)|Oui|Pour des cibles Windows et Android, vous pouvez utiliser les outils MSTest intégrés. Pour exécuter des tests unitaires sur Windows, Android et iOS, Xamarin recommande NUnit. Consultez [Configuration de TFS pour Xamarin](http://developer.xamarin.com/guides/cross-platform/ci/configuring_tfs/) (site web Xamarin).|  
|[Utiliser UI Automation pour tester votre code](../test/use-ui-automation-to-test-your-code.md)|Windows uniquement|L’enregistreur de test d’IU de Visual Studio est réservé à Windows. Pour toutes les plateformes, consultez [Xamarin Test Recorder](https://www.xamarin.com/test-cloud/recorder).|  
  
## <a name="improve-code-quality"></a>Améliorer la qualité du code  
 Lien de référence : **[Améliorer la qualité du code](/visualstudio/test/improve-code-quality)**  
  
|Fonctionnalité|Prise en charge par Xamarin|Commentaires supplémentaires|  
|-------------|----------------------------|-------------------------|  
|[Analyse de la qualité d’un code managé](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)|Oui||  
|[Recherche du code dupliqué à l’aide de la détection de clone de code](http://msdn.microsoft.com/Library/a97cd5a6-5ffa-4104-9627-8e59e513654d)|Oui||  
|[Mesures de la complexité et de la facilité de maintenance du code managé](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Oui||  
|[Explorateur de performances](../profiling/performance-explorer.md)|Non|Utilisez le [Profileur Xamarin](http://developer.xamarin.com/guides/cross-platform/deployment,_testing,_and_metrics/) par le biais de Xamarin Studio à la place. Notez que Xamarin Profiler est actuellement disponible en version préliminaire et qu'il ne fonctionne pas pour le moment avec les cibles Windows.|  
|[Analyser les problèmes de mémoire liés au .NET Framework](https://msdn.microsoft.com/en-us/library/dn342825.aspx)|Non|Visual Studio Tools n’a pas de hook au framework Mono pour le profilage.|  
  
## <a name="release-management"></a>Gestion des versions  
 Lien de référence : **[Automatiser les déploiements avec Release Management](https://msdn.microsoft.com/library/vs/alm/release/overview)**  
  
|Fonctionnalité|Prise en charge par Xamarin|Commentaires supplémentaires|  
|-------------|----------------------------|-------------------------|  
|Gérer les processus de publication des versions|Oui||  
|Déploiement sur des serveurs pour le chargement de version test via des scripts|Oui||  
|Télécharger vers le magasin d'applications|Partial|Il existe des extensions qui peuvent automatiser ce processus pour certains magasins d’applications.  Consultez [Extensions pour Visual Studio Team Services](https://marketplace.visualstudio.com/VSTS), par exemple l’[extension pour Google Play](https://marketplace.visualstudio.com/items?itemName=ms-vsclient.google-play).|  
  
## <a name="monitor-with-hockeyapp"></a>Analyser avec HockeyApp  
 Lien de référence : **[Analyser avec HockeyApp](https://www.hockeyapp.net/features/)**  
  
|Fonctionnalité|Prise en charge par Xamarin|Commentaires supplémentaires|  
|-------------|----------------------------|-------------------------|  
|Analyse des incidents, télémétrie et distribution des bêta|Oui||