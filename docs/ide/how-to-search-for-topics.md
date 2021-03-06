---
title: "Guide pratique pour rechercher des rubriques | Microsoft Docs"
ms.custom: 
ms.date: 11/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-help-viewer
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 683f1b0c-1551-4bba-91fe-3855f03fdd69
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ec4ec1c06d6c64a344e9e39d01c850b901534af8
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-search-for-topics"></a>Guide pratique pour rechercher des rubriques
Vous pouvez utiliser la fonctionnalité de recherche en texte intégral pour trouver toutes les rubriques qui contiennent un mot particulier. Si vous le souhaitez, affinez et personnalisez également votre recherche à l’aide d’expressions génériques, d’opérateurs logiques et d’opérateurs de recherche avancée.  
  
Pour ouvrir l’onglet Rechercher, choisissez l’onglet **Rechercher** dans la fenêtre de la visionneuse d’aide ou, si vous préférez utiliser le clavier, choisissez **Ctrl+E**.  
  
## <a name="to-perform-a-full-text-search"></a>Pour effectuer une recherche en texte intégral 
1.  Dans la zone de recherche, tapez le mot à rechercher.  
  
2.  Dans la requête de recherche, spécifiez les opérateurs logiques ou de recherche avancée à appliquer à la recherche, le cas échéant. Pour effectuer la recherche dans toute l’aide disponible, n’utilisez pas d’opérateurs.  
  
    > [!NOTE]
    >  Dans la boîte de dialogue **Options de la visionneuse**, vous pouvez définir des préférences supplémentaires, par exemple, pour spécifier le nombre maximal de résultats de la recherche à afficher et si le contenu en anglais doit être affiché quand votre langue principale n’est pas l’anglais.  
  
3.  Choisissez la touche **Entrée**.  
  
     Une recherche retourne 200 occurrences au maximum, par défaut, et les affiche dans la zone de résultats de la recherche. Des informations de version supplémentaires pour chaque résultat peuvent s’afficher en fonction du contenu.  
  
4.  Pour afficher une rubrique, choisissez son titre dans la liste des résultats.

## <a name="full-text-search-tips"></a>Conseils de recherche en texte intégral
Pour créer des recherches ciblées qui retournent uniquement les rubriques qui vous intéressent, vous devez comprendre comment la syntaxe affecte votre requête. La syntaxe inclut les caractères spéciaux, les mots réservés et les filtres. Cette rubrique fournit des conseils, des procédures et des informations détaillées sur la syntaxe pour vous aider à mieux écrire vos requêtes.
  
### <a name="general-guidelines"></a>Indications générales  
Le tableau suivant présente quelques règles de base et des instructions pour le développement de requêtes de recherche dans l’Aide.  
  
|Syntaxe|Description|  
|------------|-----------------|  
|Respect de la casse|Les recherches ne respectent pas la casse. Développez vos critères de recherche à l’aide de caractères majuscules ou minuscules. Par exemple, « OLE » et « ole » retournent les mêmes résultats.|  
|Combinaisons de caractères|Vous ne pouvez pas rechercher uniquement des lettres (a-z) ou des nombres (0-9). Si vous tentez de rechercher certains mots réservés, tels que « and », « from » ou « with », ils sont ignorés. Pour plus d’informations, consultez [Mots ignorés dans les recherches](#stopwords), plus loin dans cette rubrique.|  
|Ordre d’évaluation|Les requêtes de recherche sont évaluées de gauche à droite.|  
  
### <a name="search-syntax"></a>Syntaxe de la recherche  
Si vous spécifiez une chaîne de recherche qui comprend plusieurs mots, tels que « mot1 mot2 » cette chaîne revient à taper « mot1 AND mot2 », qui retourne uniquement les rubriques qui contiennent tous les mots de la chaîne de recherche.  
  
> [!IMPORTANT]
> - Les recherches d’expressions ne sont pas prises en charge. Si vous spécifiez plusieurs mots dans une chaîne de recherche, les rubriques retournées contiennent tous les mots que vous avez spécifiés, mais pas nécessairement l’expression exacte que vous avez spécifiée.  
> - Utilisez des opérateurs logiques pour spécifier la relation entre les mots dans votre expression de recherche. Vous pouvez inclure des opérateurs logiques, tels que AND, OR, NOT et NEAR, pour affiner votre recherche. Par exemple, si vous recherchez « déclarer NEAR union », les résultats de recherche incluent les rubriques dans lesquelles les mots « déclarer » et « union » ne sont séparés que de quelques mots. Pour plus d’informations, consultez [Opérateurs logiques dans les expressions de recherche](../ide/logical-operators-in-search-expressions.md).  
  
### <a name="filters"></a>Filtres  
Vous pouvez restreindre davantage les résultats de la recherche en utilisant des opérateurs de recherche avancée. L’Aide inclut trois catégories que vous pouvez utiliser pour filtrer les résultats d’une recherche en texte intégral : titre, code et mot clé.
  
### <a name="ranking-of-search-results"></a>Classement des résultats de la recherche  
L’algorithme de recherche applique certains critères pour aider à classer les résultats de la recherche dans la liste des résultats. En général :  
  
1.  Le contenu qui comprend les mots à rechercher dans le titre a un classement plus élevé.  
  
2.  Le contenu dans lequel les mots à rechercher sont situés à proximité les uns des autres a un classement plus élevé.  
  
3.  Le contenu où la densité de mots à rechercher est supérieure a un classement plus élevé.  
  
### <a name="stopwords">Mots ignorés dans les recherches (mots vides)</a>
Les mots ou les nombres courants, parfois appelés mots vides, sont automatiquement ignorés lors d’une recherche en texte intégral. Par exemple, si vous recherchez l’expression « pass through », les résultats de la recherche affichent les rubriques qui contiennent le mot « pass », mais pas « through ».  
  
## <a name="see-also"></a>Voir aussi
[Opérateurs logiques et avancés](../ide/logical-operators-in-search-expressions.md)  
[Guide pratique pour rechercher des rubriques dans l’index](../ide/how-to-find-topics-in-the-index.md)  
[Guide pratique pour rechercher des rubriques dans la table des matières](../ide/how-to-find-topics-in-the-table-of-contents.md)  
[Microsoft Help Viewer](../ide/microsoft-help-viewer.md)