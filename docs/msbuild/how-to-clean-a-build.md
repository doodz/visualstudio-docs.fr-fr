---
title: "Guide pratique pour nettoyer une génération | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Exec task [MSBuild]
- MSBuild, cleaning a build
- directories [.NET Framework], for output items
- output, removing items
ms.assetid: 999ba473-b0c4-45c7-930a-63ea7a510509
caps.latest.revision: "13"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 2b935e0d09bb80347ee17c796f83846cef02a39f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-clean-a-build"></a>Guide pratique pour nettoyer une génération
Quand vous nettoyez une build, tous les fichiers intermédiaires et de sortie sont supprimés ; seuls les fichiers projet et de composants sont conservés. De nouvelles instances des fichiers intermédiaires et de sortie peuvent alors être générées à partir des fichiers projet et de composants. La bibliothèque de tâches courantes qui est fournie avec [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] inclut une tâche [Exec](../msbuild/exec-task.md) que vous pouvez utiliser pour exécuter des commandes système. Pour plus d’informations sur la bibliothèque de tâches, consultez [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md).  
  
## <a name="creating-a-directory-for-output-items"></a>Création d’un répertoire pour les éléments de sortie  
 Par défaut, le fichier .exe qui est créé quand vous compilez un projet est placé dans le même répertoire que les fichiers projet et les fichiers sources. En général, les éléments de sortie sont cependant créés dans un répertoire distinct.  
  
#### <a name="to-create-a-directory-for-output-items"></a>Pour créer un répertoire pour les éléments de sortie  
  
1.  Utilisez l’élément `Property` pour définir l’emplacement et le nom du répertoire. Par exemple, créez un répertoire nommé `BuiltApp` dans le répertoire qui contient les fichiers projet et les fichiers sources :  
  
     `<builtdir>BuiltApp</builtdir>`  
  
2.  Utilisez la tâche [MakeDir](../msbuild/makedir-task.md) pour créer le répertoire s’il n’existe pas. Exemple :  
  
     `<MakeDir Directories = "$(builtdir)"`  
  
     `Condition = "!Exists('$(builtdir)')" />`  
  
## <a name="removing-the-output-items"></a>Suppression des éléments de sortie  
 Avant de créer de nouvelles instances des fichiers intermédiaires et de sortie, vous pouvez si nécessaire effacer toutes les instances précédentes de ces fichiers. Utilisez la tâche [RemoveDir](../msbuild/removedir-task.md) pour supprimer d’un disque un répertoire, ainsi que tous les fichiers et répertoires qu’il contient.  
  
#### <a name="to-remove-a-directory-and-all-files-contained-in-the-directory"></a>Pour supprimer un répertoire et tous les fichiers contenus dans le répertoire  
  
-   Utilisez la tâche `RemoveDir` pour supprimer le répertoire. Exemple :  
  
     `<RemoveDir Directories="$(builtdir)" />`  
  
## <a name="example"></a>Exemple  
 L’exemple de projet de code suivant contient une nouvelle cible `Clean`, qui utilise la tâche `RemoveDir` pour supprimer un répertoire, ainsi que tous les fichiers et répertoires qu’il contient. De plus, dans cet exemple, la cible `Compile` crée un répertoire distinct pour les éléments de sortie qui sont supprimés quand la build est nettoyée.  
  
 `Compile` est défini comme cible par défaut et est donc utilisée automatiquement, sauf si vous spécifiez une ou plusieurs cibles différentes. Vous utilisez le commutateur de ligne de commande **/target** pour spécifier une autre cible. Exemple :  
  
 `msbuild <file name>.proj /target:Clean`  
  
 Le commutateur **/target** peut être abrégé en **/t** et vous pouvez spécifier plusieurs cibles. Par exemple, pour utiliser la cible `Clean`, puis la cible `Compile`, tapez :  
  
 `msbuild <file name>.proj /t:Clean;Compile`  
  
```xml  
<Project DefaultTargets = "Compile"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <PropertyGroup>  
        <!-- Set the application name as a property -->  
        <name>HelloWorldCS</name>  
  
        <!-- Set the output folder as a property -->  
        <builtdir>BuiltApp</builtdir>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <!-- Specify the inputs by type and file name -->  
        <CSFile Include = "consolehwcs1.cs"/>  
    </ItemGroup>  
  
    <Target Name = "Compile">  
        <!-- Check whether an output folder exists and create  
        one if necessary -->  
        <MakeDir Directories = "$(builtdir)"   
            Condition = "!Exists('$(builtdir)')" />  
  
        <!-- Run the Visual C# compiler -->  
        <CSC Sources = "@(CSFile)"   
            OutputAssembly = "$(BuiltDir)\$(appname).exe">  
            <Output TaskParameter = "OutputAssembly"  
                ItemName = "EXEFile" />  
        </CSC>  
  
        <!-- Log the file name of the output file -->  
        <Message Text="The output file is @(EXEFile)"/>  
    </Target>  
  
    <Target Name = "Clean">  
        <RemoveDir Directories="$(builtdir)" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Exec, tâche](../msbuild/exec-task.md)   
 [MakeDir, tâche](../msbuild/makedir-task.md)   
 [RemoveDir, tâche](../msbuild/removedir-task.md)   
 [Tâche Csc](../msbuild/csc-task.md)   
 [Cibles](../msbuild/msbuild-targets.md)