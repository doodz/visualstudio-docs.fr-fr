---
title: "Afficher les données associées dans les applications WPF | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: 3aa80194-0191-474d-9d28-5ec05654b426
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: acd88eb0d4a485f01f9ced8cc1d2b2cebd182a71
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2017
---
# <a name="display-related-data-in-wpf-applications"></a>Afficher les données associées dans les applications WPF
Dans certaines applications, vous souhaiterez éventuellement utiliser des données provenant de plusieurs tables ou entités qui sont liés entre eux dans une relation parent-enfant. Par exemple, vous souhaiterez peut-être afficher une grille qui montre les clients d’un `Customers` table. Lorsque l’utilisateur sélectionne un client spécifique, une autre grille affiche les commandes de ce client à partir d’un `Orders` table.

Vous pouvez créer des contrôles liés aux données qui affichent les données connexes en faisant glisser des éléments depuis la **des Sources de données** fenêtre vers le Concepteur WPF.

## <a name="to-create-controls-that-display-related-records"></a>Pour créer des contrôles qui affichent des enregistrements connexes

1. Sur le **données** menu, cliquez sur **afficher les Sources de données** pour ouvrir le **des Sources de données** fenêtre.

2. Cliquez sur **ajouter une nouvelle Source de données**, terminez la **Configuration de Source de données** Assistant.

3. Ouvrez le Concepteur WPF et vous assurer que le concepteur contient un conteneur qui est une cible de déplacement valide pour les éléments de la **des Sources de données** fenêtre.

     Pour plus d’informations sur les cibles de déplacement valides, consultez [WPF de lier des contrôles aux données dans Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

4. Dans le **des Sources de données** fenêtre, développez le nœud qui représente la table parente ou de l’objet dans la relation. La table parent ou l’objet se trouve sur le côté « un » d’une relation un-à-plusieurs.

5. Faites glisser le nœud parent (ou tous les éléments individuels dans le nœud parent) de la **des Sources de données** fenêtre vers une cible de déplacement valide dans le concepteur.

     Visual Studio génère du code XAML qui crée des contrôles liés aux données pour chaque élément que vous faites glisser. Le code XAML ajoute également un nouveau <xref:System.Windows.Data.CollectionViewSource> pour l’objet pour les ressources de la cible de déplacement ou de la table parente. Pour certaines sources de données, Visual Studio génère également du code pour charger les données dans la table parent ou l’objet. Pour plus d’informations, consultez [WPF de lier des contrôles aux données dans Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

6. Dans le **des Sources de données** fenêtre, recherchez la table enfant connexe ou l’objet. Tables et objets enfants connexes apparaissent sous forme de nœuds extensibles en bas de la liste du nœud parent de données.

7. Faites glisser le nœud enfant (ou tous les éléments individuels dans le nœud enfant) de la **des Sources de données** fenêtre vers une cible de déplacement valide dans le concepteur.

     Visual Studio génère du code XAML qui crée de nouveaux contrôles liés aux données pour chacun des éléments que vous faites glisser. Le code XAML ajoute également un nouveau <xref:System.Windows.Data.CollectionViewSource> pour la table enfant ou l’objet pour les ressources de la cible de dépôt. Cette nouvelle <xref:System.Windows.Data.CollectionViewSource> est liée à la propriété de la table parent ou l’objet que vous venez de faire glisser vers le concepteur. Pour certaines sources de données, Visual Studio génère également du code pour charger les données dans la table enfant ou l’objet.

     La figure suivante illustre le **commandes** table de la **clients** table dans un jeu de données dans le **des Sources de données** fenêtre.

     ![Fenêtre Sources de données montrant la relation](../data-tools/media/datasources2.gif "DataSources2")

## <a name="see-also"></a>Voir aussi
[Lier des contrôles WPF à des données dans Visual Studio](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)   
[Créer des tables de recherche dans des applications WPF](../data-tools/create-lookup-tables-in-wpf-applications.md)