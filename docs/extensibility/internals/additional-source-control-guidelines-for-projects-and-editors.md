---
title: "Instructions de contrôle sources supplémentaires pour les projets et les éditeurs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], guidelines for projects and editors
ms.assetid: 2483cce5-321c-4d3c-9c5c-ee8385263f74
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4ed84b4b1bf6c974f22682dcb8d899208c653ebc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="additional-source-control-guidelines-for-projects-and-editors"></a>Instructions de contrôle sources supplémentaires pour les projets et les éditeurs
Il existe un certain nombre d’instructions qui les éditeurs et les projets doivent respecter pour prendre en charge le contrôle de code source.  
  
## <a name="guidelines"></a>Recommandations  
 Votre projet ou l’éditeur doit également les étapes ci-après pour prendre en charge le contrôle de code source :  
  
|Zone|Projet|Éditeur|Détails|  
|----------|-------------|------------|-------------|  
|Copies privées de fichiers|X||L’environnement prend en charge les copies privées de fichiers. Autrement dit, chaque personne inscrite dans le projet a sa propre copie privée des fichiers dans le projet.|  
|Persistance de l’ANSI/Unicode|X|X|Si vous écrivez le code de persistance, conserver les fichiers dans le format ANSI, car la plupart des programmes de contrôle de code source ne prennent pas en charge Unicode.|  
|Énumérer les fichiers|X||Le projet doit contenir une liste spécifique de tous les fichiers qu’il contient et doit être en mesure d’énumérer la liste des fichiers à l’aide de la <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2> ou <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (VSH_PROPID_First_Child/Next_Sibling). Le projet doit également exposer des noms d’élément par son <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.GetMkDocument%2A> mise en œuvre et la prise en charge la recherche de nom (y compris les fichiers spéciaux) via son <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.IsDocumentInProject%2A> implémentation.|  
|Format de texte|X|X|Lorsque cela est possible, les fichiers doivent être au format texte pour prendre en charge de la fusion des versions différentes. Les fichiers qui ne sont pas au format texte ne peut pas être fusionnées ultérieurement avec d’autres versions du fichier. Le format de texte par défaut est XML.|  
|En fonction de référence|X||Projets basés sur la référence sont immédiatement prises en charge dans le contrôle de code source. Toutefois, basée sur Active projets sont également pris en charge par le contrôle de code source tant que le projet peut produire une liste de ses fichiers à la demande, quel que soit l’existent de ces fichiers sur le disque. Lorsque vous ouvrez un projet à partir du contrôle de code source, le fichier projet est arrêté avant un de ses fichiers.|  
|Conserver les objets et propriétés dans l’ordre prévisible|X|X|Conserver vos fichiers dans un ordre prédéfini, par exemple par ordre alphabétique, pour faciliter la fusion.|  
|Recharger|X|X|Lorsqu’un fichier change sur le disque, votre éditeur doit être en mesure de recharger. Si vous participez au contrôle de code source, l’environnement sera recharger les données pour vous en appelant votre <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> implémentation. Le cas de recharger la plus difficile est lorsqu’une extraction se produit lorsque vous avez appelé IVsQueryEditQuerySave ::<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> et traitement des informations. Toutefois, votre code recharger doit être en mesure d’exécuter dans cette situation.<br /><br /> L’environnement recharge automatiquement les fichiers de projet. Toutefois, un projet doit implémenter <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2> si elle est imbriquée pour prendre en charge le rechargement des hiérarchies imbriquées fichiers projet.|  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge du contrôle de code source](../../extensibility/internals/supporting-source-control.md)