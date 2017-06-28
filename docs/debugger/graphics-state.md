---
title: "&#201;tat graphique | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.graphics.statewindow"
ms.assetid: 97e7757e-c372-4626-8149-99a81367a0e1
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# &#201;tat graphique
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

La fenêtre État dans Visual Studio Graphics Diagnostics vous permet de comprendre l'état graphique actif au moment de l'événement, par exemple un appel de dessin.  
  
## Présentation de la fenêtre État  
 La fenêtre État regroupe les informations sur l'état du rendu, et les présente de manière hiérarchique, dans un seul emplacement.  Selon la version de Direct3D que votre application utilise, les informations présentées dans la fenêtre État peuvent comporter des différences.  
  
### Affichages des états  
 Vous pouvez afficher la table des états de plusieurs façons différentes :  
  
|Afficher|Description|  
|--------------|-----------------|  
|Affichage des états d'entrée API|Cet affichage présente l'état dans une disposition semblable à celle des objets Direct3D qui composent l'état.|  
|Affichage des états d'entrée logiques|Cet affichage présente l'état selon une vue logique qui ne reflète pas la disposition des objets Direct3D qui composent l'état.|  
|Affichage des états épinglés|Au lieu d'une hiérarchie, l'affichage des états épinglés présente les éléments d'états épinglés dans une liste plate avec des noms complets.  Cet affichage permet de voir de nombreux éléments d'état provenant de différents ensembles d'états sur un nombre réduit de lignes.|  
  
##### Pour modifier l'affichage des états  
  
-   Dans la fenêtre État, dans le coin supérieur gauche juste en dessous de la barre de titre, choisissez le bouton qui correspond au style d'affichage d'état à utiliser.  
  
    -   **Afficher la vue des états de l'entrée API**  
  
    -   **Afficher la vue des états logiques**  
  
    -   **Afficher la vue des états épinglés**  
  
> [!IMPORTANT]
>  Vous devez épingler l'état dans **Afficher la vue des états de l'entrée API** ou dans **Afficher la vue des états logiques** pour qu'il s'affiche dans **Afficher la vue des états épinglés**.  
  
### Format de la table des états  
 La fenêtre État affiche plusieurs colonnes d'informations.  
  
|Colonne|Description|  
|-------------|-----------------|  
|Nom|Nom de l'élément d'état.  Si cet élément représente un ensemble d'états, vous pouvez développer l'élément pour l'afficher.<br /><br /> Dans l'**affichage des états d'entrée API** et dans l'**affichage des états logiques**, les noms sont mis en retrait pour montrer la relation hiérarchique qui existe entre les états.<br /><br /> Dans l'état **Affichage des états épinglés**, les noms complets sont affichés dans une liste plate.|  
|Valeur|Valeur de l'élément d'état.|  
|Type|Type de l'élément d'état.|  
  
### État modifié  
 L'état graphique change généralement de façon incrémentielle entre les appels de dessin suivants. Par ailleurs, toutes sortes de problèmes de rendu se produisent quand l'état est changé de manière incorrecte.  Pour faciliter la recherche de l'état qui a changé depuis le précédent appel de dessin, l'état modifié est marqué avec un astérisque et s'affiche en rouge. Cela s'applique non seulement à l'état lui\-même, mais également à son élément d'état parent, ce qui vous permet d'identifier facilement l'état modifié et de descendre ensuite dans la hiérarchie.  
  
### Épinglage de l'état  
 Dans la mesure où de nombreuses applications effectuent le rendu d'objets similaires de façon séquentielle, en changeant un ensemble d'états connus, il est parfois utile d'épingler sur place les états qui varient pour mieux voir leur évolution durant le passage d'un appel de dessin à un autre.  
  
 Cela peut également être utile si vous avez isolé la source d'un problème en raison de la modification d'un état particulier.  
  
##### Pour épingler l'état sur place  
  
1.  Dans la fenêtre État, recherchez l'état qui vous intéresse.  Vous devrez peut\-être développer l'état de niveau supérieur pour trouver les détails qui vous intéressent.  
  
2.  Placez le curseur sur l'état qui vous intéresse.  Une icône d'épingle s'affiche à gauche de l'élément d'état.  
  
3.  Choisissez l'icône d'épingle pour épingler l'élément d'état sur place.