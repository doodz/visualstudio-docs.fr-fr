---
title: "Afficher un instantané à l’aide d’IntelliTrace étape-back - Visual Studio | Documents Microsoft"
ms.custom: 
ms.date: 12/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c60d929-d993-49dc-9db3-43b30be9912b
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c05905e8ffeec3aa699aac9dfa46c4b017b86be5
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2017
---
# <a name="view-snapshots-using-intellitrace-step-back"></a>Afficher des instantanés à l’aide d’IntelliTrace étape différée
Événement d’étape, IntelliTrace différée étape prend automatiquement un instantané de votre application à chaque point d’arrêt et le débogueur. Les instantanés enregistrés permettent de revenir en arrière pour les points d’arrêt précédents ou étapes et afficher l’état de l’application tel qu’il était dans le passé. IntelliTrace d’étape différée peut faire gagner du temps quand vous souhaitez afficher l’état précédent de l’application mais ne souhaitez pas redémarrer le débogage ou de recréer l’état de l’application souhaitée.

Étape différée IntelliTrace est disponible à partir de Visual Studio de Enterprise 2017 15,5 et versions ultérieures, et nécessite le mise à jour anniversaire Windows 10 ou version ultérieure. La fonctionnalité est actuellement pris en charge pour le débogage ASP.NET, Windows Forms, WPF, les applications console gérés et bibliothèques de classes managées. Débogage des applications ASP.NET Core, .NET Core ou UWP n’est pas pris en charge actuellement. 
  
## <a name="enable-intellitrace-events-and-snapshots-mode"></a>Activer le mode d’événements et les instantanés IntelliTrace 
Pour activer la fonctionnalité, accédez à **Outils > Options > IntelliTrace** paramètres et sélectionnez l’option **IntelliTrace événements et les instantanés**. 

![Activer le mode d’événements IntelliTrace et les instantanés](../debugger/media/intellitrace-enable-snapshots.png "mode activer les événements IntelliTrace et les instantanés")

IntelliTrace prend un instantané du processus de l’application de débogueur de chaque événement d’étape et le point d’arrêt. Ces événements sont enregistrés dans le **événements** onglet dans le **outils de Diagnostic** fenêtre, ainsi que d’autres événements IntelliTrace. Pour ouvrir cette fenêtre, choisissez **déboguer / Windows / afficher les outils de Diagnostic**.

Une icône de caméra s’affiche en regard des événements pour lesquels les instantanés sont disponibles. 

![Onglet événements avec des instantanés](../debugger/media/intellitrace-events-tab-with-snapshots.png "onglet événements avec des instantanés sur les points d’arrêt et étapes")

Pour des raisons de performances, les instantanés ne sont pas prises lorsque vous parcourez très rapidement. Si aucune icône de caméra s’affiche en regard de l’étape, essayez d’exécuter pas à pas plus lentement.

## <a name="navigate-and-view-snapshots"></a>Naviguer et afficher des instantanés

Vous pouvez naviguer entre les événements à l’aide de la **arrière (Alt + [)** et **avant (Alt +])** boutons dans la barre d’outils de débogage. Ces boutons Parcourir les événements qui s’affichent dans le **événements** onglet dans le **fenêtre Outils de Diagnostic**. Pas à pas détaillé vers l’arrière ou vers l’avant à un événement automatiquement Active le débogage d’historique sur l’événement sélectionné.

![Revenir en arrière et transférer des boutons](../debugger/media/intellitrace-step-back-icons-description.png "boutons arrière et avancer")

Lorsque vous reculer ou avancez, Visual Studio entre en mode débogage historique. Dans ce mode, le contexte du débogueur passe à l’heure où l’événement sélectionné a été enregistré. Visual Studio déplace également le pointeur vers la ligne de code dans la fenêtre source correspondante. 

Dans cette vue, vous pouvez inspecter les valeurs dans le **pile des appels**, **variables locales**, **automatique**, et **espion** windows. Vous pouvez également pointer sur les variables pour afficher les DataTips et effectuer l’évaluation de l’expression dans le **exécution** fenêtre. Les données que vous consultez provient de l’instantané du processus de l’application effectuée à ce stade dans le temps.

Ainsi, par exemple, si vous avez atteint un point d’arrêt et de franchir une étape (**F10**), la **arrière** insère Visual Studio en mode historique à la ligne de code correspondant au point d’arrêt. 

![Mode historique d’activation sur un événement avec un instantané](../debugger/media/intellitrace-historical-mode-with-snapshot.png "mode historique d’activation sur un événement avec un instantané")

Pour revenir à l’exécution en direct, choisissez **continuer (F5)** ou cliquez sur le **revenir au débogage réel** lien dans la barre d’informations. 

Vous pouvez également afficher un instantané à partir de la **événements** onglet. Sélectionnez un événement avec un instantané, cliquez sur **activer le débogage d’historique**. Vous pouvez également cliquer sur l’icône de l’appareil photo pour activer le débogage d’historique.

![Activer le débogage d’historique d’un événement](../debugger/media/intellitrace-activate-historical-debugging.png "activer le débogage d’historique d’un événement")

Contrairement à la **définir l’instruction suivante** commande, affichage d’un instantané ne réexécutez votre code ; il vous donne une vue statique de l’état de l’application à un point dans le temps qui s’est produite dans le passé.

![Vue d’ensemble de l’étape IntelliTrace différée](../debugger/media/intellitrace-step-back-overview.png "vue d’ensemble de IntelliTrace étape différée")

## <a name="next-steps"></a>Étapes suivantes  
 Pour savoir comment inspecter des variables dans Visual Studio, consultez [visite guidée des fonctionnalités du débogueur](../debugger/debugger-feature-tour.md)  
 Pour une vue d’ensemble du débogage d’historique, consultez [le débogage d’historique](../debugger/historical-debugging.md).  

## <a name="frequently-asked-questions"></a>Questions fréquemment posées

#### <a name="how-is-intellitrace-step-back-different-from-intellitrace-events-only-mode"></a>Comment les IntelliTrace étape différée est différent du mode d’uniquement les événements IntelliTrace ?

IntelliTrace en mode uniquement des événements vous permet d’activer le débogage d’historique sur les points d’arrêt et les étapes du débogueur. Toutefois, IntelliTrace capture uniquement les données dans le **variables locales** et **automatique** windows si les fenêtres sont ouvertes, et il capture uniquement les données qui sont développées et dans la vue. En mode uniquement d’événements, souvent inutile une vue complète des variables et les objets complexes. En outre, expression d’évaluation et affichage des données dans le **espion** fenêtre n’est pas prise en charge. 

En mode d’événements et les instantanés, IntelliTrace capture l’intégralité de l’instantané du processus de l’application, y compris les objets complexes. Sur une ligne de code, vous pouvez voir les mêmes informations que si vous ont été arrêtées à un point d’arrêt (et il n’a pas d’importance si vous avez développé précédemment les informations). Évaluation de l’expression est également pris en charge lors de l’affichage d’un instantané.  

#### <a name="what-is-the-performance-impact-of-this-feature"></a>Quel est l’impact sur les performances de cette fonctionnalité ? 

L’impact sur les performances globales de pas à pas dépend de votre application. La surcharge d’une capture instantanée est environ 30 ms. Lorsqu’un instantané est activé, le processus d’application est dupliquée et la copie ramifiée est suspendue. Lorsque vous affichez un instantané, Visual Studio s’attache à la copie ramifiée du processus. Pour chaque instantané, Visual Studio copie uniquement la table de la page et définit les pages à la copie sur écriture. Si les objets sur le tas changent entre les étapes du débogueur avec des captures instantanées associées, la table des pages respectifs est ensuite copiée, aboutissant à un coût de la mémoire minimale. Si Visual Studio détecte qu’il n’existe pas d’assez de mémoire pour prendre un instantané, il ne prend pas un.
 
## <a name="known-issues"></a>Problèmes connus  
* Si vous utilisez le mode d’événements et les instantanés IntelliTrace sur les versions de Windows antérieure à la mise à jour Windows 10 automne créateurs (RS3), et si la cible de plateforme de débogage de l’application est définie sur x86, IntelliTrace n’accepte pas les captures instantanées.

    Solution de contournement :
    * Installer ou mettre à niveau vers Windows 10 automne créateurs de mise à jour (RS3). 
    * Vous pouvez également : 
        1. Installez l’ensemble d’outils VC ++ 2015.3 v140 du composant poste de travail (x86, x64) à partir du programme d’installation de Visual Studio.
        2. Générez l’application cible.
        3. À partir de la ligne de commande, utilisez l’outil editbin pour définir le `Largeaddressaware` indicateur pour l’exécutable cible. Par exemple, vous pouvez utiliser cette commande (après la mise à jour le chemin d’accès) : cette option de « C:\Program Files (x86) \Microsoft Visual Studio\Preview\Enterprise\VC\Tools\MSVC\14.12.25718\bin\Hostx86\x86\editbin.exe » « C:\Path\To\Application\app.exe ».
        4. Pour démarrer le débogage, appuyez sur **F5**. À présent, instantanés sur les points d’arrêt et les étapes du débogueur.

        > [!Note]
        > Le `Largeaddressaware` indicateur doit être défini à chaque fois que le fichier exécutable est régénéré avec les modifications.

* Lorsqu’un instantané du processus de l’application est activé sur une application qui utilise un fichier mappé en mémoire persistant, le processus de l’instantané détient un verrou exclusif sur le fichier mappé en mémoire (même une fois que le processus parent a publié son verrou). D’autres processus sont toujours en mesure de lire, mais non écrire, dans le fichier mappé en mémoire.

    Solution de contournement :
    * Désactivez toutes les captures instantanées en mettant fin à la session de débogage. 

* Lors de l’enregistrement d’un fichier avec **Déboguer > IntelliTrace > session IntelliTrace d’enregistrer** en mode d’événements et les instantanés, les données supplémentaires capturées à partir d’instantanés ne sont pas disponibles dans le fichier .itrace. Sur les événements de point d’arrêt et l’étape, vous consultez les mêmes informations que si vous aviez enregistré le fichier en mode d’uniquement les événements IntelliTrace. 
