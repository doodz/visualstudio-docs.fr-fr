---
title: "Porter, migrer et mettre à niveau des projets Visual Studio |Microsoft Docs"
ms.custom: 
ms.date: 04/28/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Win8ExpressDesktopBlock
- w8trefactor
- VS.ReviewProjectAndSolutionChangesDialog.UpgradeRetarget
- ProjectCompatibilityDlgHelpTopic
- VS.ReviewProjectAndSolutionChangesDialog.Upgrade
helpviewer_keywords:
- conversion, projects
- asset compatibility
- projects, conversion
ms.assetid: bee759bd-6ff5-4c2e-913a-ea7d3c906c29
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 1512a12a163e38aaa1b1d02dab1c2b99f5c9b344
ms.openlocfilehash: ce24abc3837047025497ccf7a58f768f90607079
ms.contentlocale: fr-fr
ms.lasthandoff: 04/28/2017

---
# <a name="port-migrate-and-upgrade-visual-studio-projects"></a>Porter, migrer et mettre à niveau des projets Visual Studio

Chaque nouvelle version de Visual Studio prend généralement en charge la plupart des précédents types de projets, de fichiers et d’autres ressources. Vous pouvez les utiliser comme à votre habitude et, si vous ne dépendez pas de fonctionnalités récentes, Visual Studio préserve la compatibilité descendante avec les versions antérieures telles que Visual Studio 2015, Visual Studio 2013 et Visual Studio 2012. (Pour connaître les fonctionnalités spécifiques à telle ou telle version, consultez les [Notes de publication](https://www.visualstudio.com/vs/release-notes/).) La prise en charge de certains types change au fil du temps, toutefois. Une version plus récente de Visual Studio peut ne plus prendre en charge certains types ou exiger qu’ils soient migrés et mis à jour avec, pour conséquence, la perte de leur compatibilité descendante. Cette rubrique fournit des détails sur les types de projets affectés dans Visual Studio 2017. Vous trouverez une liste des types pris en charge pour Visual Studio 2017 dans la rubrique [Ciblage et compatibilité de la plateforme](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs).

> [!Note]
> L’ouverture de certains types de projets nécessite l’ajout de la charge de travail approprié par le biais du programme d’installation de Visual Studio.


## <a name="projects"></a>Projets

La liste suivante décrit la prise en charge dans Visual Studio 2017 pour les projets qui ont été créés dans des versions antérieures. Si un type de projet ou de fichier n’y est pas listé alors qu’il devrait l’être, consultez la [version Visual Studio 2015 de cette rubrique](https://msdn.microsoft.com/library/hh266747.aspx) et laissez une remarque dans la section Commentaires plus bas.

| Type de projet | Assistance |
| --- | --- |
| Projets .NET Core (.xproj) | Les projets créés avec Visual Studio 2015 utilisaient des outils d’aperçu incluant un fichier de projet .xproj. Quand vous ouvrez un fichier .xproj avec Visual Studio 2017, vous êtes invité à migrer le fichier vers le format .csproj (une sauvegarde du fichier .xproj est effectuée). Ce format .csproj pour les projets .NET Core n’est pas pris en charge dans VS 2015 et antérieur.  Le format .xproj n’est pas pris en charge dans Visual Studio 2017, sauf pour la migration vers .csproj. Pour plus d’informations, consultez l’article [Migration de projets .NET Core au format .csproj](https://docs.microsoft.com/dotnet/articles/core/migration/#visual-studio-2017).|
| Application web ASP.NET et application web ASP.NET Core avec Application Insights activé | Pour chaque utilisateur de Visual Studio, les informations sur les ressources sont stockées dans le Registre pour chaque instance utilisateur. Elles sont utilisées quand l’utilisateur n’a pas de projet ouvert et qu’il souhaite explorer des données Azure Application Insights. Visual Studio 2015 n’utilise pas le même emplacement du Registre que Visual Studio 2017 et n’entre pas en conflit.<br/><br/>Une fois qu’un utilisateur crée une application web ASP.NET ou une Application web ASP.NET Core, la ressource est stockée dans le fichier .suo. L’utilisateur peut ouvrir le projet dans Visual Studio 2015 ou 2017 et les informations de ressource serviront dans les deux cas tant que Visual Studio prend en charge les projets et solutions utilisés dans les deux versions. Les utilisateurs doivent s’authentifier une seule fois sur chaque produit. Par exemple, si un projet est créé avec Visual Studio 2015 et ouvert dans Visual Studio 2017, l’utilisateur doit s’authentifier sur Visual Studio 2017. |
| C#/Visual Basic Webform ou Windows Form | Vous pouvez ouvrir le projet dans Visual Studio 2017 et Visual Studio 2015. |
| Projets de test unitaire de base de données (.csproj, .vbproj)    | Les anciens projets de test unitaire de données sont chargés dans Visual Studio 2017, mais ils utilisent la version de dépendances placée dans le GAC. Pour mettre à niveau le projet de test unitaire afin d’utiliser les dernières dépendances, cliquez avec le bouton droit sur le projet dans l’Explorateur de solutions, puis sélectionnez **Convertir en projet de tests unitaires SQL Server...**. |
| F# | Visual Studio 2017 peut ouvrir les projets créés dans Visual Studio 2013 et 2015. Pour activer les fonctionnalités de Visual Studio 2017 dans ces projets, toutefois, ouvrez les propriétés du projet et définissez la cible fsharp.core sur F# 4.1. |
| InstallShield<br/>Installation de MSI | Les projets d’installation créés dans Visual Studio 2010 peuvent être ouverts dans les versions ultérieures à l’aide de [l’extension des projets d’installation Visual Studio](https://marketplace.visualstudio.com/items?itemName=UnniRavindranathan-MSFT.MicrosoftVisualStudio2013InstallerProjects). Vous pouvez également gérer ces projets avec [InstallShield Limited Edition](https://blogs.msdn.microsoft.com/visualstudio/2013/08/15/whats-new-in-visual-studio-2013-and-installshield-limited-edition/). |
| LightSwitch | LightSwitch n’est plus pris en charge dans Visual Studio 2017. Les projets créés avec Visual Studio versions 2012 et antérieures et ouverts dans Visual Studio 2013 ou Visual Studio 2015 sont mis à niveau et ne peuvent être ouverts par la suite que dans Visual Studio 2013 ou Visual Studio 2015. |
| Microsoft Azure Tools pour Visual Studio | Pour ouvrir ces types de projets, installez tout d’abord le [kit SDK Microsoft Azure pour .NET.](http://azure.microsoft.com/downloads/), puis ouvrez le projet. Si nécessaire, votre projet est mis à jour. |
| Framework du modèle ASP.NET MVC (Model-View-Controller) | Prise en charge des versions MVC et de Visual Studio :<ul><li>Visual Studio 2010 SP1 prend en charge MVC 2 et MVC 3, tandis que la prise en charge de MVC 4 est ajoutée par le biais du [téléchargement d’ASP.NET 4 MVC 4 pour Visual Studio 2010 SP1](https://www.microsoft.com/download/details.aspx?id=30683).</li><li>Visual Studio 2012 prend en charge uniquement MVC 3 et MVC 4.</li><li>Visual Studio 2013 prend en charge uniquement MVC 4 et MVC 5.</li><li>Visual Studio 2017 et Visual Studio 2015 prennent en charge MVC 4 (vous pouvez ouvrir des projets existants, mais pas en créer) et MVC 5.</li></ul><br/><br/>Mise à niveau de versions MVC :<ul><li>Pour plus d’informations sur la mise à niveau automatique de MVC 2 vers MCV 3, consultez [ASP.NET MVC 3 Application Upgrader](http://go.microsoft.com/fwlink/?LinkID=238178).</li><li>Pour plus d’informations sur la mise à niveau manuelle de MVC 2 vers MVC 3, consultez [Mise à niveau d’un projet ASP.NET MVC 2 vers ASP.NET MVC 3 Tools Update](http://go.microsoft.com/fwlink/?linkid=238178).</li><li>Pour plus d’informations sur la mise à niveau manuelle de MVC3 vers MVC 4, consultez [Mise à niveau d'un projet ASP.NET MVC 3 vers ASP.NET MVC 4](http://www.asp.net/whitepapers/mvc4-release-notes). Si votre projet cible .NET Framework 3.5 SP1, vous devez le rediriger pour utiliser .NET Framework 4.</li><li>Pour plus d’informations sur la mise à niveau manuelle de MVC 4 vers MVC 5, consultez [How to Upgrade an ASP.NET MVC 4 and Web API Project to ASP.NET MVC 5 and Web API 2](https://www.asp.net/mvc/overview/releases/how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2) (Guide pratique pour mettre à niveau un projet ASP.NET MVC 4 et API Web vers ASP.NET MVC 5 et API Web 2).</li></ul> |
| Modélisation | Si vous permettez à Visual Studio de mettre à jour le projet automatiquement, vous pouvez l’ouvrir dans Visual Studio 2015, Visual Studio 2013 ou Visual Studio 2012.<br/><br/>Le format du projet de modélisation n’a pas changé entre Visual Studio 2015 et Visual Studio 2017, et vous pouvez ouvrir et modifier le projet dans les deux versions. Toutefois, il existe des différences de comportement dans Visual Studio 2017 :<ul><li>Les projets de modélisation sont désormais appelés projets « Validation de dépendance » dans les menus et les modèles.</li><li>Les diagrammes UML ne sont plus pris en charge dans Visual Studio 2017. Les fichiers UML demeurent répertoriés dans l’Explorateur de solutions, mais s’ouvrent en tant que fichiers XML. Utilisez Visual Studio 2015 pour afficher, créer ou modifier des diagrammes UML.</li><li>Dans Visual Studio 2017, la validation des dépendances architecturales n’est plus effectuée pendant la génération du projet de modélisation, mais à chaque génération d’un projet de code. Ce changement n’affecte pas le projet de modélisation, mais il nécessite des modifications dans les projets de code en cours de validation. Visual Studio 2017 peut effectuer automatiquement les modifications nécessaires dans les projets de code ([plus d’informations](http://go.microsoft.com/fwlink/?LinkId=827800)).</li></ul> |
| Installation de MSI (.vdproj) | Consultez la section ci-dessus relative aux projets InstallShield. | 
| Office 2007 VSTO | Requiert une mise à niveau définitive pour Visual Studio 2017. |
| Office 2010 VSTO | Si le projet cible .NET Framework 4, vous pouvez l’ouvrir dans Visual Studio 2010 SP1 et les versions ultérieures. Tous les autres projets nécessitent une mise à niveau définitive. |
| SharePoint 2010 | Lorsqu’un projet de solution SharePoint sera ouvert avec Visual Studio 2017, il sera mis à niveau vers SharePoint 2013 ou SharePoint 2016. La charge de travail « Développement .NET Desktop » doit être installée dans Visual Studio 2017 pour la mise à niveau.<br/><br/>Pour plus d’informations sur la mise à niveau des projets SharePoint, consultez les articles [Mettre à niveau vers SharePoint 2013](https://technet.microsoft.com/library/cc303420.aspx), [Mettre à jour le flux de travail dans SharePoint Server 2013](https://technet.microsoft.com/library/dn133867.aspx) et [Créer une batterie de serveurs SharePoint Server 2016 pour une mise à niveau d’attachement de base de données](https://technet.microsoft.com/library/cc263026(v=office.16).aspx). |
| SharePoint 2016 | Les projets de complément SharePoint créés dans Office Developer Tools Preview 2 ne peuvent pas être ouverts dans Visual Studio 2017. Pour contourner ce problème, vous devrez mettre à jour `MinimumVisualStudioVersion` avec la valeur 12.0 et `MinimumOfficeToolsVersion` avec la valeur 12.2 dans le fichier `.csproj` ou `.vbproj`. |
| Silverlight | Les projets Silverlight ne sont pas pris en charge dans Visual Studio 2017. Pour gérer des applications Silverlight, continuez à utiliser Visual Studio 2015. |
| SQL Server Reporting Services, SQL Server Analysis Services (SSDT, SSAS, MSAS, SSDT) | La prise en charge de ces types de projets est assurée par le biais de deux extensions de la galerie Visual Studio : [Microsoft Analysis Services Modeling Projects](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects) et [Microsoft Report Projects for Visual Studio](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio). |
| Visual C++ | Vous pouvez utiliser Visual Studio 2017 pour ouvrir des solutions et des projets créés dans Visual Studio 2015, mais les projets qui ont été créés dans des versions antérieures de Visual Studio peuvent nécessiter une mise à niveau ou un reciblage vers un ensemble d’outils plus récent pour être générés avec Visual Studio 2017. Pour plus d’informations, consultez [Guide du portage et de la mise à niveau de Visual C++](https://docs.microsoft.com/cpp/porting/visual-cpp-porting-and-upgrading-guide). |
| Extensibilité de Visual Studio/VSIX | Un projet pour lequel le paramètre MinimumVersion est défini sur 14.0 ou moins est mis à jour pour déclarer 15.0 comme version minimale, ce qui empêche son ouverture dans les versions antérieures de Visual Studio. Pour permettre l’ouverture d’un projet dans les versions antérieures, définissez MinimumVersion sur `$(VisualStudioVersion)`. Consultez aussi [Guide pratique pour migrer les projets d’extensibilité vers Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md). |
| Visual Studio Lab Management | Vous pouvez utiliser Microsoft Test Manager ou Visual Studio 2010 SP1 et versions ultérieures pour ouvrir les environnements créés dans une de ces versions. Toutefois, dans le cas de Visual Studio 2010 SP1, pour pouvoir créer des environnements, la version de Microsoft Test Manager doit correspondre à la version de Team Foundation Server. |
| Visual Studio Tools pour Apache Cordova |Ce projet peut être ouvert dans Visual Studio 2017, mais il n’est pas rétrocompatible. Quand vous ouvrez un projet à partir de Visual Studio 2015, vous êtes invité à autoriser que des modifications soient apportées à votre projet. Grâce à cette mise à niveau, le projet utilise des ensembles d’outils au lieu d’un fichier `taco.json` pour gérer le contrôle de version de la bibliothèque Cordova, ses plateformes et plug-ins, ainsi que ses dépendances nœud/npm. Pour plus d’informations, consultez le [guide de migration](http://taco.visualstudio.com/docs/vs-taco-2017-migration/). |
| Windows Communication Foundation, Windows Workflow Foundation | Vous pouvez ouvrir ce projet dans Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 et Visual Studio 2012. |
| Windows Presentation Foundation | Vous pouvez ouvrir ce projet dans Visual Studio 2013, Visual Studio 2012 et Visual Studio 2010 SP1. |
| Applications Windows Store/Phone | Les projets pour Windows Store 8.1 et 8.0, et Windows Phone 8.1 et 8.0, ne sont pas pris en charge par Visual Studio 2017. Pour gérer ces applications, continuez à utiliser Visual Studio 2015. Pour gérer les projets Windows Phone 7.x, utilisez Visual Studio 2012. |
