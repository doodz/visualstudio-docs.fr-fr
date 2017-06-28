---
title: "D&#233;bogage de projets Office"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "projets Excel (développement Office dans Visual Studio), débogage"
  - "projets Word (développement Office dans Visual Studio), débogage"
  - "Outlook (développement Office dans Visual Studio), débogage"
  - "débogage (développement Office dans Visual Studio), projets Outlook"
  - "projets Office (développement Office dans Visual Studio), débogage"
  - "Outlook (développement Office dans Visual Studio), projets"
ms.assetid: e360b9e9-9f36-48f0-a0c5-a6980fb47a87
caps.latest.revision: 52
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 48
---
# D&#233;bogage de projets Office
  Vous pouvez déboguer des projets Office à l'aide des mêmes outils Microsoft [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] que ceux que vous utilisez pour d'autres projets [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Les fonctionnalités du débogueur [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]telles que la capacité d'insérer des points d'arrêt et d'afficher des variables dans la fenêtre **Variables locales**, sont également disponibles lorsque vous déboguez des projets Office. Pour plus d’informations sur les outils de débogage [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], consultez [Débogage dans Visual Studio](../debugger/debugging-in-visual-studio.md).  
  
> [!TIP]  
>  Pour simplifier le débogage, fermez toutes les instances ouvertes de l'application Office avant de la générer et de la déboguer.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## Démarrage et arrêt du débogueur  
 Pour commencer à déboguer un projet Office, procédez de la même manière que pour d'autres projets [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ; par exemple, vous pouvez appuyer sur la touche F5. Quand vous commencez à déboguer un projet de complément VSTO, un nouveau processus pour l’application Office ciblée démarre. Par ailleurs, le complément VSTO se charge.  
  
 Lorsque vous commencez à déboguer un projet de niveau document, le document ou le classeur s'ouvre dans un nouveau processus Word ou Excel.  
  
 Lorsque vous arrêtez le débogueur, ce dernier met brusquement fin au processus d'application, ou se détache si vous l'avez configuré pour cela. Tous les autres documents ouverts dans le processus d'application Office arrêté sont également fermés sans avertissement, et les modifications non enregistrées sont perdues. Cela inclut tous les documents ou classeurs qui sont ouverts pendant que le débogueur est en cours d'exécution.  
  
 En général, il est préférable de se détacher du processus avant d'arrêter le débogueur, afin de pouvoir quitter l'application Office de manière normale. Vous pouvez également vous détacher d'abord du processus si vous souhaitez toujours utiliser un document ou une feuille de calcul après l'arrêt du débogueur.  
  
 Si vous déboguez une personnalisation au niveau du document pour Word, l'arrêt répété du débogueur et la fermeture soudaine de Word peuvent endommager le modèle Normal. Si cela se produit, vous pouvez supprimer le modèle Normal endommagé : il sera automatiquement recréé à la prochaine ouverture de Word. Toutefois, les macros qui étaient stockées dans le modèle Normal ne sont pas recréées.  
  
### Déboguer des compléments Office 2013 VSTO à l’aide d’Office 2013 ou d’Office 2016  
 Si vous utilisez Visual Studio 2015, et que les deux versions d'Office sont installées côte à côte, Visual Studio démarre Office 2016. Si vous utilisez Visual Studio 2013, Visual Studio démarre Office 2013.  
  
 Si vous voulez déboguer votre complément VSTO à l’aide d’une autre version d’Office \(2013 ou 2016\), ouvrez le **Concepteur de projets**, et sous l’onglet **Déboguer**, choisissez la case d’option **Démarrer le programme externe**. Accédez ensuite à l'emplacement de l'exécutable d'application Office approprié.  
  
## Comportement des touches F10 et F11  
 Lorsque vous commencez à déboguer un projet Office, F10 et F11 n'ont pas le même comportement que lorsque vous commencez à déboguer d'autres projets Visual Basic ou C\#. Dans les projets Visual Basic ou C\#, le débogueur s'arrête sur la fonction principale \(main\) ; dans des projets Office, Visual Studio n'a pas le contrôle sur la fonction principale de l'application Office. Toutefois, pendant le débogage, F10 et F11 ont les mêmes fonctions que dans des projets Visual Basic et C\#.  
  
## Affichage d'exceptions  
 En raison de la façon dont le code managé interagit avec le code non managé, Visual Studio n'affiche pas les erreurs générées par les applications Microsoft Office. Par exemple, si un complément VSTO créé à l’aide des outils de développement Office dans Visual Studio lève une exception, l’application Microsoft Office poursuit son exécution sans afficher d’erreur. Pour consulter ces erreurs, configurez le débogueur pour qu'il s'arrête sur les exceptions Common Language Runtime. Pour plus d'informations, consultez [Comment : arrêter l'exécution lorsqu'une exception est levée](~/misc/how-to-break-when-an-exception-is-thrown.md).  
  
 Si vous configurez le débogueur pour qu'il s'arrête sur les exceptions Common Langage Runtime, toutes les exceptions s'arrêteront alors dans le débogueur, y compris celles que vous avez gérées et certaines exceptions de première chance du runtime lui\-même, qui peuvent ne pas concerner votre projet. Des erreurs faisant référence au fait que msosec est introuvable apparaissent dans chaque projet, mais peuvent être ignorées en toute sécurité. Ces exceptions msosec n'affecteront pas votre solution.  
  
 Vous pouvez également utiliser des instructions **Try...Catch** autour de vos méthodes pour intercepter les exceptions.  
  
 Par défaut, Visual Studio n'affiche pas non plus les erreurs de débogage juste\-à\-temps pour les projets Office ; toutefois, vous pouvez activer cette fonctionnalité pour consulter les erreurs générées. Pour plus d'informations, consultez [Débogage just-in-time dans Visual Studio](../debugger/just-in-time-debugging-in-visual-studio.md).  
  
## Arguments de la ligne de commande  
 Si l'option **Action de démarrage** dans la page de propriétés **Déboguer** a la valeur **Démarrer le projet**, Visual Studio n'utilise pas d'arguments de ligne de commande lors du débogage du projet, même si vous avez spécifié des arguments de ligne de commande comme options de démarrage. Si vous souhaitez utiliser des arguments de ligne de commande lorsque vous démarrez le débogage, vous devez sélectionner une **Action de démarrage** autre que **Démarrer le projet**.  
  
## Contrôle de code source  
 Les propriétés de débogage ne sont pas partagées entre plusieurs utilisateurs sous contrôle de code source. Les projets Visual Basic et C\# stockent les propriétés de débogage dans un fichier spécifique à l'utilisateur \(*Nom\_projet*.vbproj.user ou *Nom\_projet*.csproj.user\), et ce fichier n'est pas sous contrôle de code source. Si plusieurs personnes effectuent un débogage, chacune d'entre elles doit entrer manuellement les propriétés de débogage.  
  
## Débogage de groupes de données mis en cache dans un projet au niveau du document  
 Chaque fois que vous générez un projet, le groupe de données est vidé et recréé. Si vous souhaitez déboguer un groupe de données mis en cache, vous devez ouvrir le document en dehors de Visual Studio, puis attacher le débogueur.  
  
## Débogage de projets de document Word basés sur le format de document Word 97\-2003 \(\*.doc\)  
 Pour déboguer un projet de document Word basé sur le format de document Word 97\-2003 \(\*.doc\), vous devez ajouter le dossier du projet à la liste des dossiers approuvés. Pour plus d’informations sur la façon de procéder, consultez [Octroi de niveaux de confiance à des documents](../vsto/granting-trust-to-documents.md).  
  
## Débogage de compléments désactivés  
 Les applications Microsoft Office peuvent désactiver les compléments VSTO qui se comportent de façon inattendue. Une application Microsoft Office désactive les compléments VSTO pour empêcher le chargement de tout code problématique chaque fois qu’elle démarre. Toutefois, il est également facile de provoquer un comportement inattendu au cours d'un débogage classique. Pour plus d’informations sur la façon de réactiver les compléments VSTO, consultez [Comment : réactiver un complément VSTO qui a été désactivé](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md).  
  
 Les applications Microsoft Office utilisent deux types de désactivation pour les compléments VSTO : dure et douce.  
  
### Désactivation dure  
 La désactivation de manière forcée peut se produire quand un complément VSTO entraîne la fermeture inattendue de l'application. Elle peut également se produire sur votre ordinateur de développement si vous arrêtez le débogueur pendant que le gestionnaire d'événements <xref:Microsoft.Office.Tools.AddIn.Startup> de votre complément VSTO est en cours d'exécution. Quand un complément VSTO a fait l’objet d’une désactivation dure, il figure dans la liste **Éléments désactivés** de l’application.  
  
 Si une application Office procède à une désactivation dure d’un complément VSTO créé à l’aide des outils de développement Office dans Visual Studio, l’application désactive uniquement le complément VSTO à l’origine de l’échec. Les autres compléments VSTO créés à l’aide des outils de développement Office dans Visual Studio pour cette application Office continuent à se charger.  
  
### Désactivation douce  
 La désactivation douce peut se produire quand un complément VSTO génère une erreur qui n’entraîne pas la fermeture inattendue de l’application. Par exemple, une application peut entraîner la désactivation douce d’un complément VSTO, si ce dernier lève une exception non gérée pendant l’exécution du gestionnaire d’événements <xref:Microsoft.Office.Tools.AddIn.Startup>. Quand un complément VSTO fait l’objet d’une désactivation douce, il apparaît dans la liste **Compléments d’applications inactifs** de l’application. Cette dernière change la valeur de l’entrée de Registre **LoadBehavior** pour le complément VSTO afin d’indiquer qu’il est déchargé. Pour plus d’informations sur l’entrée de Registre **LoadBehavior**, consultez [Entrées de Registre pour les compléments VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
## Résolution des erreurs d'installation à l'aide de l'observateur d'événements  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] écrit des messages dans l'observateur d'événements de Windows, pour toutes les exceptions levées lors de l'installation ou de la désinstallation des solutions Office. Vous pouvez utiliser ces messages pour résoudre les éventuels problèmes d'installation et de déploiement.  
  
## Résolution des erreurs de démarrage à l'aide d'un fichier journal et des messages d'erreur  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] peut consigner toutes les erreurs qui se produisent au démarrage dans un fichier journal ou afficher chacune d'elles dans une boîte de message. Par défaut, ces options sont désactivées. Vous pouvez les activer en créant des variables d'environnement.  
  
 Pour afficher chaque erreur dans une boîte de message, créez une variable d'environnement nommée `VSTO_SUPPRESSDISPLAYALERTS` et affectez\-lui la valeur 0 \(zéro\). Vous pouvez supprimer les messages en supprimant la variable d'environnement ou en lui affectant la valeur 1 \(un\).  
  
 Pour consigner les erreurs dans un fichier journal, créez une variable d'environnement appelée `VSTO_LOGALERTS` et affectez\-lui la valeur 1 \(un\).[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] crée le fichier journal dans le dossier qui contient le manifeste de déploiement du complément VSTO, ou dans le dossier qui contient le document ou le classeur associé à la personnalisation. En cas d'échec, le [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] crée le fichier journal dans le dossier local %TEMP%. Pour les compléments VSTO de niveau application, le nom par défaut est *Nom\_complément*.vsto.log. Pour les projets de niveau document, le nom du fichier journal est *Nom\_document*.*extension*.log ; par exemple, ExcelWorkbook1.xlsx.log. Pour arrêter la journalisation des erreurs, supprimez la variable d'environnement ou affectez\-lui la valeur 0 \(zéro\).  
  
## Voir aussi  
 [Génération de solutions Office](../vsto/building-office-solutions.md)   
 [Comment : réactiver un complément VSTO qui a été désactivé](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md)   
 [Programmation de compléments VSTO](../vsto/programming-vsto-add-ins.md)  
  
  