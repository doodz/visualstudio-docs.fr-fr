---
title: "MarkupCompilePass2, tâche | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- performing second-pass markup [WPF MSBuild], MarkupCompilePass2 task
- MarkupCompilePass2 task [WPF MSBuild]
- MarkupCompilePass2 task [WPF MSBuild], parameters
ms.assetid: 1d25689a-d21f-4b05-be26-95aa0ed4fd03
caps.latest.revision: 7
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 79460291e91f0659df0a4241e17616e55187a0e2
ms.openlocfilehash: 8635b408edc4b8088ce04a18388a0da44e9cb435
ms.lasthandoff: 02/22/2017

---
# <a name="markupcompilepass2-task"></a>MarkupCompilePass2, tâche
La tâche <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> effectue la compilation du balisage de deuxième passe sur les fichiers [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] qui référencent des types dans le même projet.  
  
## <a name="task-parameters"></a>Paramètres de tâche  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`AlwaysCompileMarkupFilesInSeparateDomain`|Paramètre **booléen** facultatif.<br /><br /> Spécifie s’il faut exécuter la tâche dans un <xref:System.AppDomain> distinct. Si ce paramètre retourne **false**, la tâche s’exécute dans le même <xref:System.AppDomain> que [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)], et elle s’exécute plus rapidement. Si le paramètre retourne **true**, la tâche s’exécute dans un deuxième <xref:System.AppDomain> isolé de [!INCLUDE[TLA2#tla_msbuild](../msbuild/includes/tla2sharptla_msbuild_md.md)] et s’exécute plus lentement.|  
|`AssembliesGeneratedDuringBuild`|Paramètre **String[]** facultatif.<br /><br /> Spécifie des références à des assemblys qui changent pendant le processus de génération. Par exemple, une solution [!INCLUDE[TLA#tla_visualstu2005](../msbuild/includes/tlasharptla_visualstu2005_md.md)] peut contenir un projet qui référence la sortie compilée d’un autre projet. Dans ce cas, la sortie compilée du deuxième projet peut être ajoutée à **AssembliesGeneratedDuringBuild**.<br /><br /> Remarque : **AssembliesGeneratedDuringBuild** doit contenir des références au jeu complet des assemblys générés par une solution de génération.|  
|`AssemblyName`|Paramètre **String** obligatoire.<br /><br /> Spécifie le nom court de l’assembly généré pour un projet. Par exemple, si un projet génère un exécutable [!INCLUDE[TLA#tla_win](../msbuild/includes/tlasharptla_win_md.md)] dont le nom est **WinExeAssembly.exe**, le paramètre **AssemblyName** a la valeur **WinExeAssembly**.|  
|`GeneratedBaml`|Paramètre de sortie **ITaskItem[]** facultatif.<br /><br /> Contient la liste des fichiers générés au format binaire [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)].|  
|`KnownReferencePaths`|Paramètre **String[]** facultatif.<br /><br /> Spécifie les références à des assemblys qui ne sont jamais modifiés pendant le processus de génération. Inclut les assemblys qui se trouvent dans le [!INCLUDE[TLA#tla_gac](../msbuild/includes/tlasharptla_gac_md.md)], dans un répertoire d’installation [!INCLUDE[TLA#tla_netframewk](../misc/includes/tlasharptla_netframewk_md.md)], et ainsi de suite.|  
|`Language`|Paramètre **String** obligatoire.<br /><br /> Spécifie le langage managé pris en charge par le compilateur. Les options valides sont **C#**, **VB**, **JScript** et **C++**.|  
|`LocalizationDirectivesToLocFile`|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie comment générer des informations de localisation pour chaque fichier [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] source. Les options valides sont **None**, **CommentsOnly** et **All**.|  
|`OutputPath`|Paramètre **String** obligatoire.<br /><br /> Spécifie le répertoire dans lequel les fichiers au format binaire [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] sont générés.|  
|`OutputType`|Paramètre **String** obligatoire.<br /><br /> Spécifie le type d’assembly généré par un projet. Les options valides sont **winexe**, **exe**, **library** et **netmodule**.|  
|`References`|Paramètre **ITaskItem[]** facultatif.<br /><br /> Spécifie la liste des références des fichiers aux assemblys qui contiennent les types qui sont utilisés dans les fichiers [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)]. L’une des références correspond à l’assembly qui a été généré par la tâche <xref:Microsoft.Build.Tasks.Windows.GenerateTemporaryTargetAssembly>, qui doit être exécutée avant la tâche <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2>.|  
|`RootNamespace`|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie l’espace de noms racine pour les classes qui se trouvent dans le projet. **RootNamespace** est également utilisé comme espace de noms par défaut d’un fichier de code managé généré quand le fichier [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] correspondant n’inclut pas l’attribut `x:Class`.|  
|`XAMLDebuggingInformation`|Paramètre **booléen** facultatif.<br /><br /> Quand la valeur est **true**, des informations de diagnostic sont générées et incluses dans le [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] compilé pour faciliter le débogage.|  
  
## <a name="remarks"></a>Remarques  
 Avant d’exécuter **MarkupCompilePass2**, vous devez générer un assembly temporaire qui contient les types utilisés par les fichiers [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dont la passe de compilation du balisage a été différée. Pour générer l’assembly temporaire, exécutez la tâche **GenerateTemporaryTargetAssembly**.  
  
 Une référence à l’assembly temporaire généré est fournie à <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> lors de son exécution, afin que les fichiers [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] dont la compilation a été différée lors de la première passe de compilation du balisage puissent maintenant être compilés au format binaire.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser la tâche <xref:Microsoft.Build.Tasks.Windows.MarkupCompilePass2> pour exécuter une deuxième passe de compilation.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MarkupCompilePass2"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MarkupCompilePass2Task">  
    <MarkupCompilePass2   
      AssemblyName="WPFMSBuildSample"  
      Language="C#"  
      OutputType="WinExe"  
      OutputPath="obj\Debug\"  
      References=".\obj\debug\WPFMSBuildSample.exe;c:\windows\Microsoft.net\Framework\v2.0.50727\System.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationCore.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\PresentationFramework.dll;C:\Program Files\Reference Assemblies\Microsoft\WinFx\v3.0\WindowsBase.dll" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur MSBuild WPF](../msbuild/wpf-msbuild-reference.md)   
 [Référence des tâches](../msbuild/wpf-msbuild-task-reference.md)   
 [Référence MSBuild](../msbuild/msbuild-reference.md)   
 [Référence des tâches](../msbuild/msbuild-task-reference.md)   
 [Génération d’une application WPF (WPF)](http://msdn.microsoft.com/Library/a58696fd-bdad-4b55-9759-136dfdf8b91c)   
 [Vue d’ensemble des applications du navigateur XAML WPF](http://msdn.microsoft.com/Library/3a7a86a8-75d5-4898-96b9-73da151e5e16)