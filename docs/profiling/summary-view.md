---
title: "Vue Résumé | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.view.summary
helpviewer_keywords:
- performance reports, summary view
- profiling tools reports, Summary view
- profiling tools, Summary view
- Summary view
ms.assetid: 98a1eb71-bbf5-4ce7-8559-cdc29f082c4b
caps.latest.revision: "37"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f07b924c5af117f39e19dc5add6046a14be22a6b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="summary-view"></a>Vue Résumé
La vue Résumé affiche des informations sur les fonctions ou les objets dont le coût est le plus pénalisant quant aux performances lors d’une exécution du profilage. Cette vue fournit un graphique chronologique et plusieurs listes de fonctions ou d’objets dont le coût est le plus pénalisant quant aux métriques de performances de la méthode de profilage. Les données de cette vue dépendent de la méthode de profilage qui a été utilisée (échantillonnage, instrumentation ou concurrence) et de l’allocation de mémoire .NET si elle a été collectée ou non.  
  
 Dans toutes les vues Résumé, à l’exception de la vue Résumé des données de concurrence, le graphique chronologique de la vue Résumé montre le pourcentage d’utilisation de l’UC de l’application profilée pendant la durée du profilage.  
  
-   Si vous spécifiez un segment de temps sur le graphique, vous pouvez réanalyser les données pour ce segment ou effectuer un zoom de l’affichage de la chronologie sur le segment que vous avez spécifié. Pour plus d’informations, consultez [Guide pratique pour filtrer les vues de rapport à partir de la chronologie Résumé](../profiling/how-to-filter-report-views-from-the-summary-timeline.md).  
  
-   Vous pouvez cliquer sur une fonction de la liste de la vue Résumé pour afficher la vue Détails de la fonction. Vous pouvez également cliquer avec le bouton droit sur la fonction pour d’autres options d’affichage.  
  
-   Pour modifier le nombre d’éléments qui apparaissent dans les listes de la vue Résumé, ouvrez le menu **Outils**, pointez sur **Options**, puis cliquez sur **Outils d’analyse des performances**. Sous **Paramètres généraux**, modifiez le paramètre **Nombre de fonctions en mode Résumé**.  
  
## <a name="notifications-links"></a>Liens Notifications  
 Vous pouvez cliquer sur les liens dans la liste Notification pour définir les options d’affichage pour le rapport. La liste est à droite du graphique chronologique.  
  
|||  
|-|-|  
|**Afficher le code autre que le code utilisateur**<br /><br /> **Afficher Uniquement mon code**|Non disponible pour le code natif ou pour les données de profilage qui ont été collectées avec la méthode d’instrumentation. Bascule entre l’affichage des données du code utilisateur uniquement (**Afficher Uniquement mon code**) et l’affichage des données de tout le code, notamment le code système (**Afficher le code autre que le code utilisateur**). Par défaut, les données sont limitées au code utilisateur. Pour changer le paramètre, consultez [Guide pratique pour filtrer les vues de rapport des outils de profilage de façon à afficher Uniquement mon code](../profiling/how-to-filter-profiling-tools-report-views-to-display-just-my-code.md).|  
|**Afficher l’aide**|Affiche les avertissements des règles de performance dans la fenêtre **Liste d’erreurs**. Pour plus d’informations, consultez [Utilisation des règles de performance pour analyser des données](../profiling/using-performance-rules-to-analyze-data.md)|  
  
## <a name="report"></a>Rapport  
 Vous pouvez cliquer sur les liens dans la liste Rapport pour ouvrir différentes vues et pour comparer, enregistrer ou filtrer le rapport. La liste est à droite du graphique chronologique.  
  
|||  
|-|-|  
|**Afficher une arborescence des appels tronquée**|Affiche les chemins d’exécution les plus consommateurs dans la vue Arborescence des appels. Pour plus d’informations, consultez [Arborescence des appels, vue](../profiling/call-tree-view.md).|  
|**Afficher les hotlines**|Non disponible pour les données de profilage qui ont été collectées avec la méthode d’instrumentation. Affiche les lignes de code source les plus consommatrices dans la vue Lignes. Pour plus d’informations, consultez [Lignes, vue](../profiling/lines-view.md).|  
|**Comparer des rapports**|Affiche la boîte de dialogue **Sélectionner des fichiers d’analyse à comparer**, où vous pouvez spécifier un autre fichier de données de profilage à comparer au fichier actif. Pour plus d’informations, consultez [Comparaison des fichiers de données de performances](../profiling/comparing-performance-data-files.md).|  
|**Exporter les données du rapport**|Affiche la boîte de dialogue **Exporter le rapport**, où vous pouvez spécifier une ou plusieurs vues de rapport à enregistrer comme fichiers .csv (valeurs séparées par des virgules) ou .xml. Pour plus d’informations, consultez [Guide pratique pour exporter les rapports des outils de profilage](http://msdn.microsoft.com/en-us/174b5bd3-df9b-4fd4-88d4-76032ab90451).|  
|**Enregistrer le rapport analysé**|Enregistre le fichier de données de profilage actif dans un fichier .vsps, qui s’ouvre plus rapidement dans l’interface pour [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Pour plus d’informations, consultez [Guide pratique pour enregistrer des fichiers de données de profilage analysés](http://msdn.microsoft.com/en-us/0340ddde-caf4-48ac-8af3-d15dcdade556).|  
|**Filtrer les données du rapport**|Affiche le volet de filtrage du rapport de profilage où vous pouvez spécifier des critères pour limiter les données de la vue Rapport. Pour plus d’informations, consultez [Filtre de la vue Rapport de performances](../profiling/performance-report-view-filter.md).|  
|**Plein écran**|Active ou désactive le mode Plein écran pour la vue Rapport.|  
  
## <a name="see-also"></a>Voir aussi  
 [Mode Résumé](../profiling/summary-view-sampling-data.md)   
 [Vue Résumé](../profiling/summary-view-instrumentation-data.md)   
 [Vue Résumé](../profiling/summary-view-dotnet-memory-data.md)