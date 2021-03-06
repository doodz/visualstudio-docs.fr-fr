---
title: Remplacer dans les fichiers, commande | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: edit.replaceinfiles
helpviewer_keywords:
- Edit.ReplaceInFiles command
- Replace In Files command
- ReplaceInFiles command
ms.assetid: f116066a-4f65-4f2c-94ef-12cbd8cfb598
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1e9ccf0c77f28d2f57d6861dd39591a7cbbce36c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="replace-in-files-command"></a>Remplacer dans les fichiers, commande
Remplace le texte dans les fichiers à l’aide d’un sous-ensemble des options proposées sous l’onglet **Remplacer dans les fichiers** de la fenêtre **Rechercher et remplacer**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Edit.ReplaceinFiles findwhat replacewith [/all] [/case]  
[/ext:extensions] [/keep] [/lookin:searchpath] [/options] [/regex]  
[/reset] [/stop] [/sub] [/text2] [/wild] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Obligatoire. Texte à rechercher.  
  
 `replacewith`  
 Obligatoire. Texte de remplacement du texte trouvé.  
  
## <a name="switches"></a>Commutateurs  
 /all ou /a  
 Facultatif. Remplace toutes les occurrences du texte recherché par le texte de remplacement.  
  
 /case ou /c  
 Facultatif. Il y a correspondance uniquement quand les caractères majuscules et minuscules correspondent exactement à ceux spécifiés dans l’argument `findwhat`.  
  
 /ext: `extensions`  
 Facultatif. Spécifie les extensions des fichiers dans lesquels effectuer la recherche.  
  
 /keep ou /k  
 Facultatif. Spécifie que tous les fichiers modifiés restent ouverts.  
  
 /lookin: `searchpath`  
 Facultatif. Répertoire dans lequel effectuer une recherche. Si le chemin contient des espaces, placez le chemin complet entre guillemets.  
  
 /options ou /t  
 Facultatif. Affiche la liste des paramètres de recherche actuels et n’effectue pas de recherche.  
  
 /regex ou /r  
 Facultatif. Utilise des caractères spéciaux prédéfinis dans l’argument `findwhat` comme notations représentant des modèles de texte, plutôt que des caractères littéraux. Pour obtenir la liste complète des caractères d’expressions régulières, consultez [Expressions régulières](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 /reset ou /e  
 Facultatif. Rétablit les paramètres par défaut des options de recherche et n’effectue pas de recherche.  
  
 /stop  
 Facultatif. Arrête l’opération de recherche en cours, le cas échant. Quand l’argument `/stop` a été spécifié, l’opération de remplacement ignore tous les autres arguments. Par exemple, pour arrêter le remplacement en cours, vous devez taper la syntaxe suivante :  
  
```  
>Edit.ReplaceinFiles /stop  
```  
  
 /sub ou /s  
 Facultatif. Recherche dans les sous-dossiers du répertoire qui est spécifié dans l’argument /lookin:`searchpath`.  
  
 /text2 ou /2  
 Facultatif. Affiche les résultats du remplacement dans la fenêtre **Résultats de la recherche 2**.  
  
 /wild ou /l  
 Facultatif. Utilise des caractères spéciaux prédéfinis dans l’argument `findwhat` comme notations représentant un caractère ou une séquence de caractères.  
  
 /word ou /w  
 Facultatif. Recherche uniquement les mots entiers.  
  
## <a name="example"></a>Exemple  
 Cet exemple recherche `btnCancel` et le remplace par `btnReset` dans tous les fichiers .cls situés dans le dossier « My Visual Studio Projects », puis affiche les informations de remplacement dans la fenêtre **Résultats de la recherche 2**.  
  
```  
>Edit.ReplaceinFiles btnCancel btnReset /lookin:"c:/my visual studio projects" /ext:.cls /text2  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Recherche et remplacement de texte](../../ide/finding-and-replacing-text.md)   
 [Remplacer dans les fichiers](../../ide/replace-in-files.md)   
 [Fenêtre Commande](../../ide/reference/command-window.md)   
 [Zone Rechercher/Commande](../../ide/find-command-box.md)   
 [Commandes Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Alias de commandes Visual Studio](../../ide/reference/visual-studio-command-aliases.md)