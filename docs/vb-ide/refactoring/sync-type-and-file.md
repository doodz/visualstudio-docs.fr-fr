---
title: Synchronisation de type et nom de fichier - refactorisation (Visual Basic) | Documents Microsoft
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff86d7bd-837b-4664-b0ea-d3ee0c52fe87
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: VB
ms.openlocfilehash: da6f39dd3573d361c1da579eb3d84c2c8ceeb517
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-in-visual-basic"></a>Synchronisation d’un type pour un nom de fichier ou un nom de fichier à un type en Visual Basic

<!-- VERSIONLESS -->
**Cette fonctionnalité est disponible dans Visual Studio 2017 et versions ultérieures.  En outre, les projets .NET Standard ne sont pas pris en charge encore pour cette opération de refactorisation.**

**Ce que :** vous permet de renommer un type pour faire correspondre le nom de fichier, ou renommer un nom de fichier pour correspondre au type qu’il contient.

**Quand :** vous avez renommé un fichier ou un type et n’avez pas encore mis à jour le fichier correspondant ou le type pour faire correspondre. 

**Pourquoi :** plaçant un type dans un fichier avec un autre nom, ou vice versa, il est difficile de trouver ce que vous cherchez.  En renommant le type ou le nom de fichier, le code devient plus lisible et plus facile d’accéder.

**Comment faire :**

1. Mettez en surbrillance ou placez le curseur de texte dans le nom du type à synchroniser :

   ![Code en surbrillance](media/synctype_highlight.png)

1. Ensuite, effectuez l’une des opérations suivantes :
   * **Clavier**
     * Appuyez sur **Ctrl +.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **changement de nom fichier *TypeName*.vb** à partir de la fenêtre de la fenêtre Aperçu, où *TypeName* est le nom du type que vous avez sélectionné.
     * Appuyez sur **Ctrl +.** pour déclencher le **Actions rapides et refactorisations** menu et sélectionnez **renommer le type à _nom de fichier_**  à partir de la fenêtre de la fenêtre Aperçu, où *Filename* est le nom du fichier actuel.
   * **Souris**
     * Cliquez sur le code, sélectionnez le **Actions rapides et refactorisations** , puis sélectionnez **changement de nom fichier *TypeName*.vb** à partir de la fenêtre de la fenêtre Aperçu, où *TypeName* est le nom du type que vous avez sélectionné.
     * Cliquez sur le code, sélectionnez le **Actions rapides et refactorisations** , puis sélectionnez **renommer le type à _nom de fichier_**  à partir de la fenêtre de la fenêtre Aperçu, où  *Nom de fichier* est le nom du fichier actuel.

   Le type ou le fichier sera renommé instantanément.  Dans l’exemple ci-dessous, le fichier **Employee.vb** a été renommé en **Person.vb** corresponde au nom du type.

   ![Résultats inline](media/synctype_result.png)

## <a name="see-also"></a>Voir aussi  
[Refactorisation (Visual Basic)](../refactoring-vb.md)
