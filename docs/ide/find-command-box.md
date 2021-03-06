---
title: Rechercher/Commande, zone | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.findcommandbox
helpviewer_keywords: Find/Command box
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8fa54e65ed581d547d7e4a0c6c5d1c1e0908c0ca
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2017
---
# <a name="findcommand-box"></a>Rechercher/Commande, zone

Vous pouvez rechercher des commandes Visual Studio de texte et d’exécution à partir de la zone **Rechercher/Commande**. La zone **Rechercher/Commande** reste disponible en tant que contrôle de barre d’outils, mais n’est plus visible par défaut. Vous pouvez afficher la zone **Rechercher/Commande** en choisissant **Ajouter ou supprimer des boutons** dans la barre d’outils **Standard**, puis en choisissant **Rechercher**.

Pour exécuter une commande [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], faites-la précéder d’un signe > (supérieur à).

La zone **Rechercher/Commande** conserve les 20 derniers éléments entrés et les affiche dans une liste déroulante. Vous pouvez parcourir la liste à l’aide des touches de direction.

![Zone Rechercher&#47;Commande](../ide/media/findcommandbox.png "FindCommandBox")

## <a name="searching-for-text"></a>Recherche de texte

Par défaut, quand vous spécifiez du texte dans la zone **Rechercher/Commande**, puis que vous choisissez la touche **Entrée**, Visual Studio recherche dans la fenêtre de document ou Outil actuelle en utilisant les options spécifiées dans la boîte de dialogue **Rechercher dans les fichiers**. Pour plus d’informations, consultez [Recherche et remplacement de texte](../ide/finding-and-replacing-text.md).

## <a name="entering-commands"></a>Entrée de commandes

Si vous voulez utiliser la zone **Rechercher/Commande** pour envoyer un alias ou une commande [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] unique plutôt que de rechercher du texte, faites précéder la commande du signe > (supérieur à). Exemple :

```
>File.NewFile c:\temp\MyFile /t:"General\Text File"
```

Vous avez également la possibilité d’utiliser la fenêtre Commande pour entrer et exécuter une ou plusieurs commandes. Certaines commandes ou certains alias peuvent être entrés et exécutés sans aucun argument, alors que d’autres ont des arguments obligatoires dans leur syntaxe. Pour obtenir la liste des commandes qui ont des arguments, consultez [Commandes Visual Studio](../ide/reference/visual-studio-commands.md).

## <a name="escape-characters"></a>Caractères d’échappement

La présence d’un signe d’insertion (^) dans une commande signifie que le caractère situé juste après ce signe est interprété littéralement, et non comme un caractère de contrôle. Ceci permet d’incorporer des guillemets ("), des espaces, des barres obliques, des accents circonflexes ou tout autre caractère littéral dans une valeur de paramètre ou de commutateur, à l’exception des noms de commutateur. Exemple :

```
>Edit.Find ^^t /regex
```

Un accent circonflexe fonctionne de la même façon, qu’il soit à l’intérieur ou en dehors des guillemets. Si un accent circonflexe est le dernier caractère de la ligne, il est ignoré.

## <a name="see-also"></a>Voir aussi

[Fenêtre Commande](../ide/reference/command-window.md)  
[Recherche et remplacement de texte](../ide/finding-and-replacing-text.md)