---
title: "RC, tâche | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- vc.task.rc
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- RC task (MSBuild (Visual C++))
- MSBuild (Visual C++), RC task
ms.assetid: 2fd26c75-a056-4dda-9f7e-2f90d3748d88
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 73e4544ab00142929bbd8d8dbdb154355c48c609
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="rc-task"></a>RC, tâche
Encapsule l’outil Compilateur de ressources Microsoft Windows (rc.exe). La tâche **RC** compile des ressources, telles que des curseurs, des icônes, des images bitmap, des boîtes de dialogue et des polices, dans un fichier de ressources (.res). Pour plus d’informations, consultez « Compilateur de ressources » sur le site web [MSDN](http://go.microsoft.com/fwlink/?LinkId=737).  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche RCtask. La plupart des paramètres de tâche, et quelques ensembles de paramètres, correspondent à une option de ligne de commande.  
  
|Paramètre|Description|  
|---------------|-----------------|  
|**AdditionalIncludeDirectories**|Paramètre **String[]** facultatif.<br /><br /> Ajoute un répertoire à la liste des répertoires dans lesquels sont recherchés les fichiers include.<br /><br /> Pour plus d’informations, lisez la section relative à l’option **/I** dans [Utilisation de RC (ligne de commande RC)](http://go.microsoft.com/fwlink/?LinkId=155730) sur le site web MSDN.|  
|**AdditionalOptions**|Paramètre de **chaîne** facultatif.<br /><br /> Liste d’options de ligne de commande, par exemple, **"***/option1 /option2 /option#*". Utilisez ce paramètre pour spécifier des options de ligne de commande qui ne sont pas représentées par un autre paramètre de tâche **RC**.<br /><br /> Pour plus d’informations, lisez la section relative aux options dans [Utilisation de RC (ligne de commande RC)](http://go.microsoft.com/fwlink/?LinkId=155730) sur le site web MSDN.|  
|**Culture**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie un ID de paramètres régionaux qui représente la culture utilisée dans les ressources.<br /><br /> Pour plus d’informations, lisez la section relative à l’option **/l** dans [Utilisation de RC (ligne de commande RC)](http://go.microsoft.com/fwlink/?LinkId=155730) sur le site web MSDN.|  
|**IgnoreStandardIncludePath**|Paramètre **booléen** facultatif.<br /><br /> Si `true`, empêche le compilateur de ressources de vérifier la variable d’environnement INCLUDE lorsqu’il recherche des fichiers d’en-tête ou des fichiers de ressources.<br /><br /> Pour plus d’informations, lisez la section relative à l’option **/x** dans [Utilisation de RC (ligne de commande RC)](http://go.microsoft.com/fwlink/?LinkId=155730) sur le site web MSDN.|  
|**NullTerminateStrings**|Paramètre **booléen** facultatif.<br /><br /> Si `true`, termine par la valeur Null toutes les chaînes de la table de chaînes.<br /><br /> Pour plus d’informations, lisez la section relative à l’option **/n** dans [Utilisation de RC (ligne de commande RC)](http://go.microsoft.com/fwlink/?LinkId=155730) sur le site web MSDN.|  
|**PreprocessorDefinitions**|Paramètre **String[]** facultatif.<br /><br /> Définissez un ou plusieurs symboles de préprocesseur pour le compilateur de ressources. Spécifiez une liste de symboles de macro.<br /><br /> Pour plus d’informations, lisez la section relative à l’option **/d** dans [Utilisation de RC (ligne de commande RC)](http://go.microsoft.com/fwlink/?LinkId=155730) sur le site web MSDN. Regardez également **UndefinePreprocessorDefinitions** dans ce tableau.|  
|**ResourceOutputFileName**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie le nom du fichier de ressources. Spécifiez un nom de fichier de ressources.<br /><br /> Pour plus d’informations, lisez la section relative à l’option **/fo** dans [Utilisation de RC (ligne de commande RC)](http://go.microsoft.com/fwlink/?LinkId=155730) sur le site web MSDN.|  
|**ShowProgress**|Paramètre **booléen** facultatif.<br /><br /> Si `true`, affiche les messages qui signale la progression du compilateur.<br /><br /> Pour plus d’informations, lisez la section relative à l’option **/v** dans [Utilisation de RC (ligne de commande RC)](http://go.microsoft.com/fwlink/?LinkId=155730) sur le site web MSDN.|  
|**Source**|Paramètre `ITaskItem[]` requis.<br /><br /> Définit un tableau d’éléments de fichier source MSBuild pouvant être consommés et émis par des tâches.|  
|**SuppressStartupBanner**|Paramètre **booléen** facultatif.<br /><br /> Si la valeur est `true`, empêche l'affichage du message de copyright et de numéro de version quand la tâche démarre.<br /><br /> Pour plus d’informations, tapez l’option de ligne de commande **/?**, puis regardez l’option **/nologo**.|  
|**TrackerLogDirectory**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie le répertoire des journaux de suivi.|  
|**UndefinePreprocessorDefinitions**|Annule la définition d’un symbole du préprocesseur.<br /><br /> Pour plus d’informations, lisez la section relative à l’option **/u** dans [Utilisation de RC (ligne de commande RC)](http://go.microsoft.com/fwlink/?LinkId=155730) sur le site web MSDN. Regardez également **PreprocessorDefinitions** dans ce tableau.|  
  
## <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les tâches](../msbuild/msbuild-task-reference.md)