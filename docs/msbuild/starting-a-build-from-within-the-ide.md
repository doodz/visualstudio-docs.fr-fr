---
title: "Démarrage d’une build à partir de l’IDE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: build
ms.assetid: 936317aa-63b7-4eb0-b9db-b260a0306196
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 081bcfd01d8c28959bf0dd4d038e91895e9c3983
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="starting-a-build-from-within-the-ide"></a>Démarrage d'une build à partir de l'IDE
Les systèmes de projet personnalisés doivent utiliser <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildManagerAccessor> pour démarrer des builds. Cette rubrique en explique les raisons et décrit la procédure.  
  
## <a name="parallel-builds-and-threads"></a>Builds et threads parallèles  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] autorise les builds parallèles, ce qui nécessite une médiation d’accès aux ressources communes. Les systèmes de projet peuvent exécuter des builds en mode asynchrone, mais ils ne doivent pas appeler de fonctions de génération à partir des rappels qui sont fournis au gestionnaire de build.  
  
 Si le système de projet modifie des variables d’environnement, il doit définir le NodeAffinity de la build sur OutOfProc. Cela signifie que vous ne pouvez pas utiliser d’objets hôtes, puisqu’ils nécessitent le nœud in-process.  
  
## <a name="using-ivsbuildmanageraccessor"></a>Utilisation d’IVSBuildManagerAccessor  
 Le code ci-dessous présente une méthode qui peut être utilisée par un système de projet pour démarrer une build :  
  
```csharp
  
public bool Build(Project project, bool isDesignTimeBuild)  
{  
    // Get the accessor from the IServiceProvider interface for the   
    // project system  
    IVsBuildManagerAccessor accessor =  
        serviceProvider.GetService(typeof(SVsBuildManagerAccessor)) as     
        IVsBuildManagerAccessor;  
    bool releaseUIThread = false;  
    try  
    {  
        if(accessor != null)  
        {  
            // Claim the UI thread under the following conditions:  
            // 1. The build must use a resource that uses the UI thread  
            // or,  
            // 2. The build requires the in-proc node AND waits on the   
            // UI thread for the build to complete  
            if(NeedsUIThread)  
            {  
                int result = accessor.ClaimUIThreadForBuild();  
                if(result != S_OK)  
                {  
                     // Not allowed to claim the UI thread right now  
                     return false;  
                }  
                releaseUIThread = true;  
             }  
             if(isDesignTimeBuild)  
             {  
// Start the design time build  
                  int result = accessor.BeginDesignTimeBuild();  
                  if(result != S_OK)  
                  {  
                      // Not allowed to begin a design-time build at  
                      // this time. Try again later.  
                      return false;  
                  }  
             }  
         }  
         bool buildSucceeded = false;  
         // perform project-system specific build set up tasks  
         // Create your BuildRequestData  
         // This assumes a IHostServices variable (hostServices) set   
   // to your host services. If you don't use a project instance   
         // (you build from a file for example) then use another   
         // constructor.  
         BuildRequestData requestData = new   
             BuildRequestData(project.CreateProjectInstance(),   
             "myTarget", hostServices,   
             BuildRequestData.BuildRequestDataFlags.None);  
         // Mark your your submission as Pending  
         BuildSubmission submission =  
              BuildManager.DefaultBuildManager.  
              PendBuildRequest(requestData);  
         // Register the loggers in BuildLoggers  
         if (accessor != null)  
         {  
               foreach (ILogger logger in BuildLoggers)  
               {  
                    accessor.RegisterLogger(submission.SubmissionId,   
                        logger);  
               }  
         }  
         BuildResult buildResult = submission.Execute();  
         return buildResult;  
     }  
     // Clean up resources  
     finally  
     {  
         if(accessor != null)  
         {  
             // Unregister the loggers, if necessary.  
             accessor.UnregisterLoggers(submission.SubmissionId);  
             // Release the UI thread, if used  
             if(releaseUIThread)  
             {  
                  accessor.ReleaseUIThreadForBuild();  
             }  
             // End the design time build, if used  
             if(isDesignTimeBuild)  
             {  
                  accessor.EndDesignTimeBuild();  
             }  
         }  
     }  
}  
  
```