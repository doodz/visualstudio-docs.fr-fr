---
title: "Tâche LIB | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLibrarianTool.Name
- VC.Project.VCLibrarianTool.TreatLibWarningsAsErrors
- VC.Project.VCLibrarianTool.Verbose
- vc.task.lib
- VC.Project.VCLibrarianTool.ErrorReporting
- VC.Project.VCLibrarianTool.LinkLibraryDependencies
- VC.Project.VCLibrarianTool.LinkTimeCodeGeneration
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), LIB task
- LIB task (MSBuild (Visual C++))
ms.assetid: e062c7f9-cc69-4a83-9361-1bb5355e5fe8
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 6bdca24340f301fc19f3bc8d1e86c97c3b98c5c5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="lib-task"></a>Tâche LIB
Encapsule l'outil Gestionnaire de bibliothèques 32 bits de Microsoft, lib.exe. Le gestionnaire de bibliothèques crée et gère une bibliothèque de fichiers objets COFF (Common Object File Format). Il peut également créer des fichiers d'exportation et des bibliothèques d'importation pour référencer des définitions exportées. Pour plus d’informations, consultez [Référence LIB](/cpp/build/reference/lib-reference) et [Exécution de LIB](/cpp/build/reference/running-lib).  
  
## <a name="parameters"></a>Paramètres  
 Le tableau ci-dessous décrit les paramètres de la tâche **LIB**. La plupart des paramètres de tâche correspondent à une option de ligne de commande.  
  
|Paramètre|Description|  
|---------------|-----------------|  
|**AdditionalDependencies**|Paramètre **String[]** facultatif.<br /><br /> Spécifie les éléments supplémentaires à ajouter à la ligne de commande.|  
|**AdditionalLibraryDirectories**|Paramètre **String[]** facultatif.<br /><br /> Substitue le chemin d’accès de la bibliothèque d’environnement. Spécifiez un nom de répertoire.<br /><br /> Pour plus d’informations, consultez l’article [/LIBPATH (Autre chemin de bibliothèque)](/cpp/build/reference/libpath-additional-libpath).|  
|**AdditionalOptions**|Paramètre de **chaîne** facultatif.<br /><br /> Liste des options lib.exe comme indiqué sur la ligne de commande. Par exemple, **«** */option1 /option2 /option#* ». Utilisez ce paramètre pour spécifier des options lib.exe qui ne sont pas représentées par un autre paramètre de tâche **LIB**.<br /><br /> Pour plus d’informations, consultez [Exécution de LIB](/cpp/build/reference/running-lib).|  
|**DisplayLibrary**|Paramètre de **chaîne** facultatif.<br /><br /> Affiche des informations sur la bibliothèque de sortie. Spécifiez un nom de fichier pour rediriger les informations vers un fichier. Spécifiez « CON » ou ne spécifiez rien pour rediriger les informations vers la console.<br /><br /> Ce paramètre correspond à l’option **/LIST** de lib.exe.|  
|**ErrorReporting**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie comment envoyer des informations d'erreur interne à Microsoft si lib.exe échoue au moment de l'exécution.<br /><br /> Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.<br /><br /> -   **NoErrorReport** - **/ERRORREPORT:NONE**<br />-   **PromptImmediately** - **/ERRORREPORT:PROMPT**<br />-   **QueueForNextLogin** - **/ERRORREPORT:QUEUE**<br />-   **SendErrorReport** - **/ERRORREPORT:SEND**<br /><br /> Pour plus d’informations, consultez l’option de ligne de commande **/ERRORREPORT** dans [Exécution de LIB](/cpp/build/reference/running-lib).|  
|**ExportNamedFunctions**|Paramètre **String[]** facultatif.<br /><br /> Spécifie une ou plusieurs fonctions à exporter.<br /><br /> Ce paramètre correspond à l’option **/EXPORT:** de lib.exe.|  
|**ForceSymbolReferences**|Paramètre de **chaîne** facultatif.<br /><br /> Force lib.exe à inclure une référence au symbole spécifié.<br /><br /> Ce paramètre correspond à l’option **/INCLUDE:** de lib.exe.|  
|**IgnoreAllDefaultLibraries**|Paramètre `Boolean` facultatif.<br /><br /> Si la valeur est `true`, supprime toutes les bibliothèques par défaut de la liste des bibliothèques dans lesquelles lib.exe recherche quand il résout des références externes.<br /><br /> Ce paramètre correspond à la forme sans paramètre de l’option **/NODEFAULTLIB de lib.exe**.|  
|**IgnoreSpecificDefaultLibraries**|Paramètre **String[]** facultatif.<br /><br /> Supprime les bibliothèques spécifiées de la liste des bibliothèques dans lesquelles lib.exe recherche quand il résout des références externes.<br /><br /> Ce paramètre correspond à l’option **/NODEFAULTLIB** de lib.exe qui prend un argument `library`.|  
|**LinkLibraryDependencies**|Paramètre `Boolean` facultatif.<br /><br /> Si la valeur est `true`, spécifie que les sorties de bibliothèque émanant des dépendances du projet sont automatiquement liées.|  
|**LinkTimeCodeGeneration**|Paramètre `Boolean` facultatif.<br /><br /> Si la valeur est `true`, spécifie la génération du code durant l'édition de liens.<br /><br /> Ce paramètre correspond à l’option **/LCTG** de lib.exe.|  
|**MinimumRequiredVersion**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie la version minimale requise du sous-système. Spécifiez la liste, délimitée par des virgules, de nombres décimaux compris entre 0 et 65535.|  
|**ModuleDefinitionFile**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie le nom du fichier de définition de module (.def).<br /><br /> Ce paramètre correspond à l’option **/DEF** de lib.exe qui prend un argument `filename`.|  
|**Nom**|Paramètre de **chaîne** facultatif.<br /><br /> Lors de la génération d'une bibliothèque d'importation, spécifie le nom de la DLL pour laquelle la bibliothèque d'importation est générée.<br /><br /> Ce paramètre correspond à l’option **/NAME** de lib.exe qui prend un argument `filename`.|  
|**OutputFile**|Paramètre de **chaîne** facultatif.<br /><br /> Remplace le nom et l'emplacement par défaut du programme que lib.exe crée.<br /><br /> Ce paramètre correspond à l’option **/OUT** de lib.exe qui prend un argument `filename`.|  
|**RemoveObjects**|Paramètre **String[]** facultatif.<br /><br /> Omet l'objet spécifié de la bibliothèque de sortie. Lib.exe crée une bibliothèque de sortie en combinant tous les objets (qu'ils se trouvent dans des fichiers objets ou des bibliothèques), puis en supprimant tous les objets spécifiés par cette option.<br /><br /> Ce paramètre correspond à l’option **/NAME** de lib.exe qui prend un argument `membername`.|  
|**Sources**|Paramètre `ITaskItem[]` requis.<br /><br /> Spécifie la liste des fichiers sources séparés par des espaces.|  
|**SubSystem**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie l'environnement pour l'exécutable. Le choix du sous-système affecte le symbole de point d'entrée ou la fonction de point d'entrée.<br /><br /> Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.<br /><br /> -   **Console** - **/SUBSYSTEM:CONSOLE**<br />-   **Windows** - **/SUBSYSTEM:WINDOWS**<br />-   **Native** - **/SUBSYSTEM:NATIVE**<br />-   **EFI Application** - **/SUBSYSTEM:EFI_APPLICATION**<br />-   **EFI Boot Service Driver** - **/SUBSYSTEM:EFI_BOOT_SERVICE_DRIVER**<br />-   **EFI ROM** - **/SUBSYSTEM:EFI_ROM**<br />-   **EFI Runtime** - **/SUBSYSTEM:EFI_RUNTIME_DRIVER**<br />-   **WindowsCE** - **/SUBSYSTEM:WINDOWSCE**Remplacer ce texte<br />-   **POSIX** - **/SUBSYSTEM:POSIX**<br /><br /> Pour plus d’informations, consultez l’article [/SUBSYSTEM (Spécifier le sous-système)](/cpp/build/reference/subsystem-specify-subsystem).|  
|**SuppressStartupBanner**|Paramètre **booléen** facultatif.<br /><br /> Si la valeur est `true`, empêche l'affichage du message de copyright et de numéro de version quand la tâche démarre.<br /><br /> Pour plus d’informations, consultez l’option **/NOLOGO** dans [Exécution de LIB](/cpp/build/reference/running-lib).|  
|**TargetMachine**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie la plateforme cible du programme ou de la DLL.<br /><br /> Spécifiez l'une des valeurs suivantes, chacune d'elles correspondant à une option de ligne de commande.<br /><br /> -   **MachineARM** - **/MACHINE:ARM**<br />-   **MachineEBC** - **/MACHINE:EBC**<br />-   **MachineIA64** - **/MACHINE:IA64**<br />-   **MachineMIPS** - **/MACHINE:MIPS**<br />-   **MachineMIPS16** - **/MACHINE:MIPS16**<br />-   **MachineMIPSFPU** -**/MACHINE:MIPSFPU**<br />-   **MachineMIPSFPU16** - **/MACHINE:MIPSFPU16**<br />-   **MachineSH4** - **/MACHINE:SH4**<br />-   **MachineTHUMB** - **/MACHINE:THUMB**<br />-   **MachineX64** - **/MACHINE:X64**<br />-   **MachineX86** - **/MACHINE:X86**<br /><br /> Pour plus d’informations, consultez l’article [/MACHINE (Spécifier la plateforme cible)](/cpp/build/reference/machine-specify-target-platform).|  
|**TrackerLogDirectory**|Paramètre de **chaîne** facultatif.<br /><br /> Spécifie le répertoire du journal de Tracker.|  
|**TreatLibWarningAsErrors**|Paramètre **booléen** facultatif.<br /><br /> Si la valeur est `true`, empêche la tâche **LIB** de générer un fichier de sortie si lib.exe génère un avertissement. Si la valeur est `false`, un fichier de sortie est généré.<br /><br /> Pour plus d’informations, consultez l’option **/WX** dans [Exécution de LIB](/cpp/build/reference/running-lib).|  
|**UseUnicodeResponseFiles**|Paramètre **booléen** facultatif.<br /><br /> Si la valeur est `true`, indique au système de projet de générer des fichiers réponse UNICODE quand le générateur de bibliothèques est créé dynamiquement. Spécifiez `true` quand les fichiers du projet ont des chemins d'accès UNICODE.|  
|**Verbose**|Paramètre **booléen** facultatif.<br /><br /> Si la valeur est `true`, affiche des détails sur la progression de la session ; ceux-ci incluent les noms des fichiers .obj en cours d'ajout. Les informations sont envoyées vers la sortie standard et peuvent être redirigées vers un fichier.<br /><br /> Pour plus d’informations, consultez l’option **/VERBOSE** dans [Exécution de LIB](/cpp/build/reference/running-lib).|  
  
## <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Task Reference (Informations de référence sur les tâches MSBuild)](../msbuild/msbuild-task-reference.md)