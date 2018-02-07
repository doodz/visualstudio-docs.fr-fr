---
title: Service Essentials | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: services, essentials
ms.assetid: fbe84ad9-efe1-48b1-aba3-b50b90424d47
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 006ab3b57a21d5b9a661f06bc984f4dca8757bfd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="service-essentials"></a>Service Essentials
Un service est un contrat entre deux VSPackages. Un VSPackage fournit un ensemble spécifique d’interfaces pour un autre VSPackage à consommer. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] est une collection de VSPackages qui fournit des services aux autres packages VS à elle-même.  
  
 Par exemple, vous pouvez utiliser le service SVsActivityLog pour obtenir une interface IVsActivityLog, que vous pouvez utiliser pour écrire dans le journal d’activité. Pour plus d’informations, consultez [Comment : utiliser le journal d’activité](../../extensibility/how-to-use-the-activity-log.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] fournit également des services intégrés qui ne sont pas enregistrés. Les VSPackages peuvent remplacer intégrés ou d’autres services en fournissant un service de remplacement. Remplacement d’un seul service est autorisée pour n’importe quel service.  
  
 Les services n’ont aucune fonctionnalité de découverte. Par conséquent, vous devez connaître l’identificateur de service (SID) d’un service que vous souhaitez utiliser, et vous devez connaître les interfaces qu’il fournit. La documentation de référence pour le service fournit ces informations.  
  
-   Les VSPackages qui fournissent des services sont appelés fournisseurs de services.  
  
-   Les services qui sont fournis pour les autres packages VS sont appelés services globaux.  
  
-   Services qui sont disponibles uniquement pour le VSPackage qui implémente les, ou à n’importe quel objet, qu'il crée, sont appelés des services locaux.  
  
-   Les services qui remplacent les services intégrés ou des services fournis par d’autres packages, sont appelés des remplacements de service.  
  
-   Des services ou des remplacements de service, sont chargées à la demande, autrement dit, le fournisseur de services est chargé quand le service à que fournir est demandé par un autre VSPackage.  
  
-   Pour prendre en charge le chargement de la demande, un fournisseur de services inscrit ses services globaux avec [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Pour plus d’informations, consultez [Comment : fournir un Service](../../extensibility/how-to-provide-a-service.md).  
  
-   Après avoir obtenu un service, utilisez [QueryInterface](/cpp/atl/queryinterface) (code non managé) ou effectuer un cast (code managé) pour obtenir l’interface de votre choix, par exemple :  
  
    ```vb  
    TryCast(GetService(GetType(SVsActivityLog)), IVsActivityLog)  
    ```  
  
    ```csharp  
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    ```  
  
-   Le code managé fait référence à un service par son type, alors que le code non managé fait référence à un service par son GUID.  
  
-   Lorsque [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] charge un VSPackage, il passe un fournisseur de services pour le VSPackage pour donner l’accès VSPackage aux services globaux. Cela est appelé « emplacement » le VSPackage.  
  
-   Les VSPackages peuvent être des fournisseurs de services pour les objets qu’ils créent. Par exemple, un formulaire peut envoyer une demande pour un service de couleur à son cadre, ce qui peut transmettre la requête [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   Les objets managés qui sont profondément imbriquées ou pas dans le site, peuvent appeler <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> pour accéder directement aux services globaux.   
  
<a name="how-to-use-getglobalservice"></a>  
  
## <a name="use-getglobalservice"></a>Utilisation d’un GetGlobalService  
  
Parfois, vous devrez peut-être obtenir un service à partir d’une fenêtre outil ou le contrôle conteneur qui n’a pas été installé, ou bien a été installé avec un fournisseur de services qui ne connaît pas sur le service souhaité. Par exemple, vous souhaiterez écrire dans le journal d’activité à partir d’un contrôle. Pour plus d’informations sur ces scénarios et d’autres, consultez [Comment : résoudre les problèmes des Services](../../extensibility/how-to-troubleshoot-services.md).  
  
Vous pouvez obtenir la plupart des services de Visual Studio en appelant la méthode statique <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> (méthode).  
  
<xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A>s’appuie sur un service de mise en cache fournisseur qui est initialisé à la première fois qu’un VSPackage dérivé de Package est placé. Vous devez vous assurer que cette condition est remplie, ou bien être préparée pour un service de type null.  
  
Heureusement, <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> fonctionne correctement la plupart du temps.  
  
-   Si un VSPackage fournit un service connu uniquement par un autre VSPackage, le VSPackage demandant le service est placé avant le VSPackage en fournissant que le service est chargé.  
  
-   Si une fenêtre outil est créée par un VSPackage, le VSPackage est placé avant la création de la fenêtre outil.  
  
-   Si un conteneur de contrôle est hébergé par une fenêtre outil créée par un VSPackage, le VSPackage est placé avant la création du conteneur de contrôle.  
  
### <a name="to-get-a-service-from-within-a-tool-window-or-control-container"></a>Pour obtenir un service à partir d’un conteneur de contrôle ou de la fenêtre outil  
  
-   Insérez ce code dans le constructeur, une fenêtre outil ou un conteneur de contrôle :  
  
    ```csharp  
    IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog;
        if (log == null) return;
    ```  
    ```vb  
    Dim log As IVsActivityLog = TryCast(Package.GetGlobalService(GetType(SVsActivityLog)), IVsActivityLog)
    If log Is Nothing Then
        Return
    End If
    ```  
    
    Ce code obtient un service SVsActivityLog et il effectue un cast en interface IVsActivityLog, qui peut être utilisée pour écrire dans le journal d’activité. Pour obtenir un exemple, consultez [Comment : utiliser le journal d’activité](../../extensibility/how-to-use-the-activity-log.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Liste des Services disponibles](../../extensibility/internals/list-of-available-services.md)   
 [À l’aide et fournir des Services](../../extensibility/using-and-providing-services.md)   
 [Cast et conversions de types](/dotnet/csharp/programming-guide/types/casting-and-type-conversions)   
 [Cast](/cpp/cpp/casting)
