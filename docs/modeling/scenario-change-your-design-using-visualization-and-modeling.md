---
title: "Scénario : Modifier votre conception à l’aide de la visualisation et de modélisation | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords:
- code visualization [Visual Studio ALM]
- modeling software [Visual Studio ALM]
- software modeling [Visual Studio ALM]
- walkthroughs [Visual Studio ALM], visualizing code
- walkthrough [Visual Studio ALM], visualizing code
- walkthrough [Visual Studio ALM], modeling software
- walkthroughs [Visual Studio ALM], modeling software
ms.assetid: ccc80825-a4a0-44fa-a0bb-f95254785a3b
caps.latest.revision: 61
author: alexhomer1
ms.author: ahomer
manager: douge
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
translationtype: Machine Translation
ms.sourcegitcommit: 3d07f82ea737449fee6dfa04a61e195654ba35fa
ms.openlocfilehash: 4f46bc8e8b4dd476e90ebd122895bb354d967795
ms.lasthandoff: 02/22/2017

---
# <a name="scenario-change-your-design-using-visualization-and-modeling"></a>Scénario : modifier votre conception à l'aide de la visualisation et de la modélisation
Assurez-vous que votre système logiciel répond aux besoins des utilisateurs à l’aide des outils de visualisation et de modélisation dans Visual Studio.
Utilisez des outils tels que des cartes de code, des diagrammes de dépendance et des diagrammes de classes pour :  
  
 Pour connaître les versions de Visual Studio prennent en charge chaque outil, consultez [prise en charge de Version pour l’architecture et les outils de modélisation](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
-   Clarifier les besoins des utilisateurs et les processus d’entreprise.  
  
-   Visualiser et explorer le code existant.  
  
-   Décrire les modifications apportées à un système existant.  
  
-   Vérifier que le système satisfait à ses spécifications.  
  
-   Maintenir la cohérence du code avec la conception.  
  
 Cette procédure pas à pas :  
  
-   décrit ce que ces outils peuvent apporter à votre projet de logiciel ;  
  
-   montre comment utiliser ces outils, quelle que soit votre approche du développement, à l’aide d’un exemple de scénario.  
  
 Pour en savoir plus sur ces outils et les scénarios qu’ils prennent en charge, consultez :  
  
-   [Analyse et modélisation de l’architecture](../modeling/analyze-and-model-your-architecture.md)  
  
-   [Visualiser du code](../modeling/visualize-code.md)  
  
##  <a name="a-namescenariooverviewa-scenario-overview"></a><a name="ScenarioOverview"></a>Présentation du scénario  
 Ce scénario décrit certaines étapes des cycles de vie du développement de logiciels dans deux entreprises fictives : Dinner Now et Lucerne Publishing. Dinner Now propose un service web de livraison de repas à Seattle. Les clients peuvent commander des repas et les payer sur le site web de Dinner Now. Les commandes sont alors envoyées au restaurant local chargé de les livrer. Lucerne Publishing, une société implantée à New York, exerce plusieurs activités liées ou non au web. Par exemple, elle gère un site web sur lequel ses clients peuvent publier leurs commentaires sur des restaurants.  
  
 Lucerne a récemment acquis Dinner Now et veut apporter les modifications suivantes :  
  
-   Intégrer le site web de Dinner Now en y ajoutant des fonctionnalités de publication d’avis sur les restaurants.  
  
-   Remplacer le système de paiement de Dinner Now par celui de Lucerne.  
  
-   Développer les services Dinner Now dans toute la région.  
  
 Dinner Now utilise SCRUM et eXtreme Programming, des outils qui offrent une couverture de test très élevée et comportent très peu de code non pris en charge. Dinner Now réduit les risques en créant des versions légères mais fonctionnelles d’un système, puis en ajoutant progressivement des fonctionnalités. Elle développe le code sur des itérations courtes et fréquentes. Cela lui permet d’intégrer les modifications en toute confiance, de refactoriser fréquemment le code et d’éviter un lourd travail de conception en amont.  
  
 Lucerne tient à jour une collection bien plus importante et complexe de systèmes,  certains d’entre eux datant de plus de 40 ans. La société fait preuve d’une grande prudence pour apporter des modifications en raison de la complexité et de la portée du code hérité. Elle suit un processus de développement plus rigoureux, préférant concevoir des solutions détaillées, et documenter la conception et les modifications effectuées pendant le développement.  
  
 Les deux équipes utilisent des diagrammes de modélisation dans Visual Studio pour développer des systèmes qui répondent mieux aux besoins des utilisateurs. Elles utilisent Team Foundation Server en parallèle d’autres outils pour planifier, organiser et gérer leur travail.  
  
 Pour plus d’informations sur Team Foundation Server, consultez :  
  
-   [Planification et suivi du travail](#PlanningTracking)  
  
-   [Test, validation et archivage du code mis à jour](#TestValidateCheckInCode)  
  
##  <a name="a-namemodelingdiagramstoolsa-roles-of-architecture-and-modeling-diagrams-in-software-development"></a><a name="ModelingDiagramsTools"></a>Rôles de l’Architecture et de modélisation de diagrammes dans le développement de logiciels  
 Le tableau suivant décrit les rôles que ces outils peuvent jouer pendant diverses étapes du cycle de développement logiciel :  
  
||**Modélisation des besoins des utilisateurs**|**Modélisation des processus d’entreprise**|**Architecture du système se conception**|**Visualisation de code se Exploration**|**Vérification**|  
|------|------------------------------------|-----------------------------------|--------------------------------------|------------------------------------------|----------------------|  
|Diagramme de langage spécifique à un domaine (DSL)|Oui|Oui|Oui|||  
|Diagramme des dépendances, la validation de couche|||Oui|Oui|Oui|  
|Carte de code|||Oui|Oui|Oui|  
|Concepteur de classes (basé sur le code)||||Oui||  
  
Pour dessiner des diagrammes de dépendance, vous devez créer un projet de modélisation dans le cadre d’une solution existante ou nouvelle. Ces diagrammes doivent être créés dans le projet de modélisation.
Éléments sur des diagrammes de dépendance sont trouvent dans le projet de modélisation, mais ils ne sont pas stockés dans le modèle commun. Les cartes de code et les diagrammes de classes .NET créés à partir du code sont externes au projet de modélisation.  
  
 Reportez-vous à :  
  
-   [Créer des diagrammes de dépendance à partir de votre code.](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Mapper les dépendances à travers vos solutions](../modeling/map-dependencies-across-your-solutions.md)  
  
-   [Guide pratique pour ajouter des diagrammes de classes aux projets (Concepteur de classes)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)  
  
-   [SDK de modélisation pour Visual Studio - Langages spécifiques à un domaine](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
  
 Les deux équipes utilisent également la validation de dépendance pour vous assurer que le code en cours de développement reste cohérent avec la conception.  
  
 Reportez-vous à :  
  
-   [Maintien du Code conforme à la conception](#ValidatingCode)  
  
-   [Décrire l’Architecture logique : diagrammes de dépendance](#DescribeLayers)  
  
-   [Valider le code avec des diagrammes de dépendance](../modeling/validate-code-with-layer-diagrams.md)  
  
    > [!NOTE]
    >  Certaines versions de Visual Studio prend en charge la validation de dépendance et des versions en lecture seule des cartes de code pour la visualisation et de modélisation. Pour connaître les versions de Visual Studio prennent en charge cette fonctionnalité, consultez [prise en charge de Version pour l’architecture et les outils de modélisation](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
##  <a name="a-nameunderstandingcommunicatinga-understanding-and-communicating-information-about-the-system"></a><a name="UnderstandingCommunicating"></a>Compréhension et la communication des informations sur le système  
 Il n’y a pas d’ordre impératif pour l’utilisation des diagrammes de modélisation Visual Studio. Vous pouvez donc les utiliser comme vous le voulez, en fonction de vos besoins ou de votre approche. En règle générale, les équipes revoient leurs modèles de façon répétée et fréquente au cours d’un projet. Chaque diagramme possède ses propres atouts pour vous aider à comprendre, décrire et communiquer différents aspects du système en cours de développement.  
  
 Les sociétés Dinner Now et Lucerne communiquent entre elles et avec les parties prenantes des projets en utilisant des diagrammes comme langage commun. Par exemple, Dinner Now utilise des diagrammes pour effectuer ces tâches :  
  
-   visualiser le code existant ;  
  
-   communiquer avec Lucerne sur les récits utilisateur nouveaux ou mis à jour ;  
  
-   identifier les modifications requises pour prendre en charge des récits utilisateur nouveaux ou mis à jour.  
  
 Lucerne utilise des diagrammes pour effectuer ces tâches :  
  
-   découvrir le processus d’entreprise de Dinner Now ;  
  
-   comprendre la conception du système ;  
  
-   communiquer avec Dinner Now sur les besoins nouveaux ou mis à jour des utilisateurs ;  
  
-   documenter les mises à jour du système.  
  
 Les diagrammes sont intégrés à Team Foundation Server pour que les équipes puissent planifier, gérer et suivre leur travail plus facilement. Par exemple, les équipes utilisent des modèles pour identifier des cas de test et des tâches de développement, et pour estimer leur travail. Lucerne lie les éléments de travail Team Foundation Server aux éléments de modèle, ce qui permet aux équipes de surveiller la progression du travail et de s’assurer que le système répond aux besoins des utilisateurs. Par exemple, la liaison de cas d’usage à des éléments de travail de cas de test permet de savoir que les cas d’usage sont remplis quand tous les tests sont réussis.  
  
 Avant que les équipes n’archivent leurs modifications, ils valident le code par rapport à la conception et les tests en exécutant des builds qui incluent la validation de dépendance et des tests automatisés. Ainsi, le code mis à jour n’entre pas en conflit avec la conception et ne nuit pas aux fonctionnalités qui étaient opérationnelles auparavant.  
  
 Reportez-vous à :  
  
-   [Identification des modifications apportées au système existant](#DeterminingChanges)  
  
-   [Maintien du code conforme à la conception](#ValidatingCode)  
  
-   [Conseils généraux pour la création et à l’aide de modèles](#GeneralTips)  
  
-   [Planification et suivi du travail](#PlanningTracking)  
  
-   [Test, validation et archivage du code mis à jour](#TestValidateCheckInCode)  

###  <a name="a-namedeterminingchangesa-identifying-changes-to-the-existing-system"></a><a name="DeterminingChanges"></a>Identification des modifications apportées au système existant  
 Dinner Now doit estimer le coût de réalisation pour remplir le nouveau besoin. Ce coût dépend en partie des répercussions de cette modification sur les autres parties du système. Pour mieux déterminer ce coût, l’un des développeurs de Dinner Now crée ces cartes et diagrammes à partir du code existant :  
  
|**Carte ou diagramme**|**Affiche**|  
|------------------------|---------------|  
|*Carte de code*<br /><br /> Reportez-vous à :<br /><br /> -   [Mapper les dépendances dans vos solutions](../modeling/map-dependencies-across-your-solutions.md)<br />-   [Parcourir et réorganiser des cartes de code](../modeling/browse-and-rearrange-code-maps.md)<br />-   [Personnaliser des cartes de code en modifiant les fichiers DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md)|Dépendances et autres relations dans le code.<br /><br /> Par exemple, Dinner Now peut commencer par examiner les cartes de code des assemblys pour avoir une vue d’ensemble des assemblys et de leurs dépendances. La société peut explorer les cartes pour examiner les espaces de noms et les classes figurant dans ces assemblys.<br /><br /> Dinner Now peut également créer des cartes pour examiner certaines zones et d’autres types de relations dans le code. Elle utilise l’Explorateur de solutions pour rechercher et sélectionner les zones et les relations qui l’intéressent.|  
|*Diagramme de classes basé sur le code*<br /><br /> Consultez la page [Comment : ajouter des diagrammes de classes aux projets (Concepteur de classes)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).|Classes existantes dans le code|  
  
 Par exemple, le développeur crée une carte de code. Il ajuste la portée pour se concentrer sur les zones concernées par le nouveau scénario. Ces zones sont sélectionnées et mises en surbrillance sur la carte :  
  
 ![Graphique de dépendance Namespace](../modeling/media/namespace_reviewsystem.png "Namespace_ReviewSystem")  
  
 **Carte de code Namespace**  
  
 Le développeur développe les espaces de noms sélectionnés pour en voir les classes, les méthodes et les relations :  
  
 ![Graphique de dépendance d’espace de noms développé](../modeling/media/dep_reviewsystem.png "Dep_ReviewSystem")  
  
 **Carte de code d’espace de noms développé avec des liens entre les groupes visibles**  
  
 Le développeur examine le code pour trouver les classes et méthodes affectées. Pour voir les effets de chaque modification apportée, régénérez les cartes de code après chaque modification. Consultez la page [visualiser le code](../modeling/visualize-code.md).  
  
 Pour décrire les modifications apportées à d’autres parties du système, notamment les composants ou les interactions, l’équipe peut dessiner ces éléments sur des tableaux blancs. Elle peut également dessiner les diagrammes suivants dans Visual Studio pour que les détails puissent être capturés, gérés et compris par les deux équipes :  
  
|**Diagrammes**|**Décrit**|  
|------------------|-------------------|  
|*Diagramme de classes basé sur le code*<br /><br /> Consultez la page [Comment : ajouter des diagrammes de classes aux projets (Concepteur de classes)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).|Classes existantes dans le code.|  
  
###  <a name="a-namevalidatingcodea-keeping-code-consistent-with-the-design"></a><a name="ValidatingCode"></a>Maintien du Code conforme à la conception  
 Dinner Now doit s’assurer que le code mis à jour demeure cohérent avec la conception. Ils créent les diagrammes de dépendance qui décrivent les couches de fonctionnalités dans le système, spécifient les dépendances autorisées entre les artefacts de solution et d’associer à ces couches.  
  
|**Diagramme**|**Décrit**|  
|-----------------|-------------------|  
|*Diagramme de dépendances*<br /><br /> Reportez-vous à :<br /><br /> -   [Créer des diagrammes de dépendance à partir de votre code.](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Diagrammes de dépendance : référence](../modeling/layer-diagrams-reference.md)<br />-   [Diagrammes de dépendance : instructions](../modeling/layer-diagrams-guidelines.md)<br />-   [Valider le code avec des diagrammes de dépendance](../modeling/validate-code-with-layer-diagrams.md)|Architecture logique du code.<br /><br /> Un diagramme de dépendances organise et mappe les artefacts d’une [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] solution à des groupes abstraits appelés *couches*. Ces couches identifient les rôles, les tâches ou les fonctions que ces artefacts effectuent dans le système.<br /><br /> Les diagrammes de couche sont utiles pour décrire la conception prévue du système et valider le code en constante évolution par rapport à cette conception.<br /><br /> Pour créer des couches, faites glisser des éléments à partir de l’Explorateur de solutions, des cartes de code, de l’affichage de classes et de l’Explorateur d’objets. Pour dessiner de nouvelles couches, utilisez la boîte à outils ou cliquez avec le bouton droit sur la surface du diagramme.<br /><br /> Pour afficher les dépendances existantes, cliquez avec le bouton droit sur la surface du diagramme de couche, puis cliquez sur **Générer des dépendances**. Pour spécifier les dépendances prévues, dessinez de nouvelles dépendances.|  
  
 Par exemple, le diagramme de dépendance suivant décrit les dépendances entre les couches et le nombre d’artefacts associés à chaque couche :  
  
 ![Diagramme de dépendances de système de paiement intégré](../modeling/media/layer_integrated_dnlucerne.png "Layer_Integrated_DNLucerne")  
  
 **Diagramme de dépendances**  
  
 Pour vous assurer que les conflits avec la conception ne se produisent pas pendant le développement de code, les équipes utilisent la validation de dépendance sur les builds qui sont exécutées sur Team Foundation Build. Ils créent également une tâche MSBuild personnalisée afin d’exiger une validation de dépendance dans leurs opérations d’archivage. Elles utilisent des rapports de build pour collecter les erreurs de validation.  
  
 Reportez-vous à :  
  
-   [Définir votre processus de génération](http://msdn.microsoft.com/Library/61593e10-d24b-492f-b19a-af4d85abea6b)  
  
-   [Utiliser un processus de build d’archivage contrôlé pour valider les modifications](http://msdn.microsoft.com/Library/9cfc8b9c-1023-40fd-8ab5-1b1bd9c172ec)  
  
-   [Personnaliser votre modèle de processus de génération](http://msdn.microsoft.com/Library/b94c58f2-ae6f-4245-bedb-82cd114f6039)  
  
###  <a name="a-namegeneraltipsa-general-tips-for-creating-and-using-models"></a><a name="GeneralTips"></a>Conseils généraux sur la création et l’utilisation de modèles  
  
-   La plupart des diagrammes sont constitués de nœuds connectés par des lignes. Pour chaque type de diagramme, la boîte à outils fournit différents types de nœuds et de lignes.  
  
     Pour ouvrir la boîte à outils, dans le menu **Affichage** , cliquez sur **Boîte à outils**.  
  
-   Pour créer un nœud, faites-le glisser de la boîte à outils vers le diagramme. Certains types de nœuds doivent être déplacés vers des nœuds existants. Par exemple, sur un diagramme de composant, un nouveau port doit être ajouté à un composant existant.  
  
-   Pour créer une ligne ou une connexion, cliquez sur l’outil approprié dans la boîte à outils, cliquez sur le nœud source, puis cliquez sur le nœud cible. Certaines lignes peuvent être créées uniquement entre certains types de nœuds. Quand vous déplacez le pointeur sur une source ou une cible possible, le pointeur indique si vous pouvez créer une connexion.  
  
###  <a name="a-nameplanningtrackinga-planning-and-tracking-work"></a><a name="PlanningTracking"></a>Planification et suivi du travail  
 Des diagrammes de modélisation Visual Studio sont intégrés à Team Foundation Server pour que vous puissiez planifier, gérer et suivre le travail plus facilement. Les deux équipes utilisent des modèles pour identifier des cas de test et des tâches de développement, et pour estimer leur travail. Lucerne crée des éléments de travail Team Foundation Server et les lie à des éléments de modèle,tels que des cas d’usage ou des composants. Ainsi, les équipes peuvent suivre leur progression et tracer le travail par rapport aux besoins des utilisateurs. Elles peuvent mieux contrôler le maintien de la cohérence des modifications avec ces besoins.  
  
 Au fur et à mesure que le travail avance, les équipes mettent à jour leurs éléments de travail pour prendre en compte le temps dévolu à leurs tâches. Elles surveillent et signalent également l’état de leur travail en utilisant les fonctionnalités Team Foundation Server suivantes :  
  
-   Des *rapports d’avancement* quotidiens qui indiquent si les équipes vont effectuer le travail planifié dans le temps imparti. Les équipes génèrent d’autres rapports similaires à partir de Team Foundation Server pour suivre la progression des bogues.  
  
-   Une *feuille de calcul d’itération* qui utilise Microsoft Excel pour aider les équipes à surveiller et équilibrer la charge de travail entre ses membres. Cette feuille de calcul est liée à Team Foundation Server et fournit le thème de discussion lors des réunions d’avancement régulières.  
  
-   Un *tableau de bord de développement* qui utilise Office Project pour tenir l’équipe informée sur les points importants du projet.  
  
 Reportez-vous à :  
  
-   [Le suivi du travail à l’aide des Services d’équipe Visual Studio ou Team Foundation Server](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503)  
  
-   [Graphiques, tableaux de bord et rapports pour Visual Studio ALM](http://msdn.microsoft.com/Library/1f28ba6c-c5e5-46d3-9209-ede24ae78e48)  
  
-   [Créez votre file d’attente et les tâches à l’aide du projet](http://msdn.microsoft.com/Library/be5cef4f-755f-4ffe-8dd7-876d1e02c330)  
  
###  <a name="a-nametestvalidatecheckincodea-testing-validating-and-checking-in-code"></a><a name="TestValidateCheckInCode"></a>Test, validation et archivage du Code  
 À mesure que les équipes effectuent chaque tâche, elles vérifient leur code dans la gestion de version Team Foundation et reçoivent des rappels de Team Foundation Server, en cas d’oubli. Avant que Team Foundation Server n’accepte leurs archivages, les équipes exécutent les tests unitaires et validation de dépendance pour vérifier le code par rapport à leur cas de test et de la conception. Team Foundation Server leur permet d’exécuter des builds, des tests unitaires automatisés et la validation de dépendance régulièrement. Ainsi, elles vérifient que le code respecte les critères suivants :  
  
-   Il fonctionne.  
  
-   Il n’empêche pas du code opérationnel existant de fonctionner.  
  
-   Il n’entre pas en conflit avec la conception.  
  
 Dinner Now possède une grande collection de tests automatisés. Lucerne peut réutiliser ces tests, car ils sont presque tous encore applicables. Lucerne peut également s’appuyer sur ces tests et en ajouter de nouveaux pour couvrir les nouvelles fonctionnalités. Les deux sociétés utilisent également Visual Studio pour exécuter des tests manuels.  
  
 Pour vous assurer que le code est conforme à la conception, les équipes configurent leurs builds dans Team Foundation Build pour inclure la validation de dépendance. En cas de conflit, un rapport détaillé est généré.  
  
 Reportez-vous à :  
  
-   [Test de l’application](https://www.visualstudio.com/docs/test/overview)  
  
-   [Valider votre système pendant le développement](../modeling/validate-your-system-during-development.md)  
  
-   [Utilisez le contrôle de version](http://go.microsoft.com/fwlink/?LinkID=525605)  
  
-   [Générer l’application](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)  
  
##  <a name="a-nameupdatingsystema-updating-the-system-using-visualization-and-modeling"></a><a name="UpdatingSystem"></a>Mise à jour de la visualisation à l’aide du système et de modélisation  
 Lucerne et Dinner Now doivent intégrer leurs systèmes de paiement. Les sections suivantes présentent les diagrammes de modélisation dans Visual Studio qui les aident à effectuer cette tâche :  
  
-   [Visualiser le Code existant : Cartes de Code](#VisualizeCode)  
  
-   [Définir un glossaire de Types : diagrammes de classes](#DefineClasses)  
  
-   [Décrire l’Architecture logique : diagrammes de dépendance](#DescribeLayers)  
  
 Reportez-vous à :  
  
-   [Visualiser du code](../modeling/visualize-code.md)  
  
-   [Utiliser des modèles dans votre processus de développement](../modeling/use-models-in-your-development-process.md)  
  
-   [Modéliser l’architecture de votre application](../modeling/model-your-app-s-architecture.md)  
 
###  <a name="a-namevisualizecodea-visualize-existing-code-code-maps"></a><a name="VisualizeCode"></a>Visualiser le Code existant : Cartes de Code  
 Les cartes de code montrent l’organisation et les relations actuelles dans le code. Les éléments sont représentés par des *nœuds* dans la carte et les relations sont représentées par des *liens*. Les cartes de code peuvent vous aider à effectuer les types de tâches suivants :  
  
-   Explorer du code méconnu.  
  
-   Comprendre où et comment une modification suggérée peut affecter du code existant.  
  
-   Rechercher des zones de complexité, des dépendances physiques ou des modèles, ou d’autres zones qui pourraient tirer profit d’amélioration du produit.  
  
 Par exemple, Dinner Now doit estimer le coût de la mise à jour du composant PaymentProcessing. Ce coût dépend en partie des répercussions de cette modification sur les autres parties du système. Pour mieux déterminer ce coût, l’un des développeurs de Dinner Now génère des cartes de code à partir du code existant et ajuste la portée pour se concentrer sur les zones éventuellement concernées par la modification.  
  
 La carte suivante montre les dépendances entre la classe PaymentProcessing et d’autres parties du système Dinner Now, qui sont mises en surbrillance :  
  
 ![Graphique de dépendance pour le système de paiement de Dinner Now](../modeling/media/dep_dnpayment.png "Dep_DNPayment")  
  
 **Carte de code pour le système de paiement de Dinner Now**  
  
 Le développeur explore la carte en développant la classe PaymentProcessing et en sélectionnant ses membres pour voir les zones éventuellement affectées :  
  
 ![Méthodes dans PaymentProcessing et dépendances](../modeling/media/depgraph_expandeddn.png "DepGraph_ExpandedDN")  
  
 **Méthodes à l’intérieur de la classe PaymentProcessing et leurs dépendances**  
  
 L’équipe génère la carte suivante pour le système de paiement de Lucerne pour inspecter ses classes, méthodes et dépendances. Elle constate que le système Lucerne risque aussi de devoir être modifié pour interagir avec les autres parties de Dinner Now :  
  
 ![Graphique de dépendance pour le système de paiement Lucerne](../modeling/media/depgraph_lucernepay.png "DepGraph_LucernePay")  
  
 **Carte de code pour le système de paiement Lucerne**  
  
 Les deux équipes travaillent ensemble pour déterminer les modifications requises pour intégrer les deux systèmes. Elles décident de refactoriser une partie du code pour faciliter sa mise à jour. La classe PaymentApprover est déplacée vers l’espace de noms DinnerNow.Business et nécessite quelques méthodes nouvelles. Les classes Dinner Now qui gèrent les transactions ont leur propre espace de noms. Les équipes créent et utilisent des éléments de travail pour planifier, organiser et suivre leur travail. Elles lient les éléments de travail à des éléments de modèle quand cela s’avère utile.  
  
 Après avoir réorganisé le code, les équipes génèrent une nouvelle carte de code pour voir la structure et les relations mises à jour :  
  
 ![Graphique de dépendance avec code réorganisé](../modeling/media/depgraph_integrated.png "DepGraph_Integrated")  
  
 **Carte de code avec code réorganisé**  
  
 Cette carte montre que la classe PaymentApprover se trouve maintenant dans l’espace de noms DinnerNow.Business et qu’elle comporte de nouvelles méthodes. Les classes de transaction Dinner Now ont maintenant leur propre espace de noms PaymentSystem, ce qui facilitera l’utilisation ultérieure de ce code.  
  
#### <a name="creating-a-code-map"></a>Création d’une carte de code  
  
-   Pour obtenir un aperçu rapide du code source, générez une carte de code en procédant comme suit :  
  
     Dans le menu **Architecture** , cliquez sur **Générer une carte du code pour la solution**.  
  
     Pour obtenir un aperçu rapide du code compilé, créez une carte de code vide, puis faites glisser des fichiers d’assembly ou des fichiers binaires vers la surface de la carte.  
  
-   Pour explorer du code spécifique ou des éléments de solution, utilisez l’Explorateur de solutions pour sélectionner les éléments et les relations que vous voulez visualiser. Vous pouvez ensuite générer une nouvelle carte ou ajouter les éléments sélectionnés à une carte existante. Consultez la page [mapper les dépendances dans vos solutions](../modeling/map-dependencies-across-your-solutions.md).  
  
-   Pour explorer la carte plus facilement, réorganisez la disposition pour qu’elle corresponde aux types de tâches à effectuer.  
  
     Par exemple, pour visualiser les couches dans le code, sélectionnez une disposition en arborescence. Consultez la page [Parcourir et réorganiser des cartes de code](../modeling/browse-and-rearrange-code-maps.md).  
  
#### <a name="summary-strengths-of-code-maps"></a>Résumé : atouts des cartes de code  
 Les cartes de code vous aident à :  
  
-   comprendre l’organisation et les relations du code existant ;  
  
-   identifier les zones qui peuvent être affectées par une modification proposée ;  
  
-   identifier des zones de complexité, des modèles, des couches ou d’autres zones à améliorer pour rendre le code plus facile à tenir à jour, modifier et réutiliser.  
  
#### <a name="relationship-to-other-diagrams"></a>Relation aux autres diagrammes  
  
|**Diagramme**|**Décrit**|  
|-----------------|-------------------|  
|Diagramme de dépendances|L’architecture logique du système. Utiliser la validation de dépendance pour vous assurer que le code reste cohérent avec la conception.<br /><br /> Pour vous aider à identifier dependencys existantes ou prévues dependencys, de créer une carte de code et de regrouper des éléments connexes. Pour créer un diagramme de dépendances, consultez :<br /><br /> -   [Créer des diagrammes de dépendance à partir de votre code.](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Diagrammes de dépendance : instructions](../modeling/layer-diagrams-guidelines.md)|  
|Diagramme de classes (basé sur le code)|Classes existantes dans le code d’un projet spécifique.<br /><br /> Pour visualiser et modifier une classe existante dans le code, utilisez le Concepteur de classes.<br /><br /> Consultez la page [Comment : ajouter des diagrammes de classes aux projets (Concepteur de classes)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).|  
  
###  <a name="a-namedefineclassesa-define-a-glossary-of-types-class-diagrams"></a><a name="DefineClasses"></a>Définir un glossaire de Types : diagrammes de classes  
 Les diagrammes de classes définissent les entités, les termes ou les concepts qui participent au système, et leurs relations. Par exemple, vous pouvez utiliser ces diagrammes pendant le développement pour décrire les attributs et les opérations de chaque classe, indépendamment de leur langage ou mode d’implémentation.  
  
 Pour permettre à Lucerne de décrire et d’étudier les entités qui participent au cas d’usage Traiter le paiement, le diagramme suivant est dessiné :  
  
 ![Entités traiter le paiement sur le diagramme de classes](../modeling/media/uml_payentities.png "UML_PayEntities")  
  
 **Entités traiter le paiement sur un diagramme de classes**  
  
 Ce diagramme montre qu’un client peut effectuer plusieurs commandes et utiliser différents modes de paiement pour les commandes. BankAccount et CreditCard héritent de Payment.  
  
 Pendant le développement, Lucerne utilise le diagramme de classes suivant pour décrire et étudier les détails de chaque classe :  
  
 ![Détails des entités de paiement sur un diagramme de classes traiter](../modeling/media/uml_payment.png "UML_Payment")  
  
 **Détails traiter le paiement sur le diagramme de classes**  
    
#### <a name="drawing-a-class-diagram"></a>Dessin d’un diagramme de classes  
 Un diagramme de classes comporte les principales fonctionnalités suivantes :  
  
-   Des types, tels que des classes, des interfaces et des énumérations :  
  
    -   Une *classe* est la définition d’objets qui partagent des caractéristiques structurelles ou comportementales spécifiques.  
  
    -   Une *interface* définit une partie du comportement extérieurement visible d’un objet.  
  
    -   Une *énumération* est un classifieur qui contient une liste de valeurs littérales.  
  
-   Les*attributs* sont des valeurs d’un type donné qui décrivent chaque instance d’un *classifieur*. Un classifieur est un nom générique attribué aux types, aux composants, aux cas d’usage et même aux acteurs.  
  
-   Les*opérations* sont des méthodes ou des fonctions que les instances d’un classifieur peuvent exécuter.  
  
-   Une *association* indique une sorte de relation entre deux classifieurs.  
  
    -   Une *agrégation* est une association qui indique une propriété partagée entre des classifieurs.  
  
    -   Une *composition* est une association qui indique une relation ensemble à partie entre des classifieurs.  
  
     Pour afficher les agrégations ou les compositions, définissez la propriété **Aggregation** sur une association. La valeur**Shared** et la valeur **Composite** affichent les agrégations et les compositions, respectivement.  
  
-   Une *dépendance* indique que la modification de la définition d’un classifieur peut modifier la définition d’un autre classifieur.  
  
-   Une *généralisation* indique qu’un classifieur spécifique hérite une partie de sa définition d’un classifieur général. Une *réalisation* indique qu’une classe implémente les opérations et attributs fournis par une interface.  
  
     Pour créer ces relations, utilisez l’outil **Héritage** . Sinon, une réalisation peut être représentée sous forme d’interface *lollipop*.  
  
-   Les*packages* sont des groupes de classifieurs, d’associations, de lignes de vie, de composants et d’autres packages. Les relations d’*importation* indiquent qu’un package inclut toutes les définitions d’un autre package.  
  
 Pour commencer l’exploration et l’examen des classes existantes, vous pouvez utiliser le Concepteur de classes pour créer des diagrammes de classes à partir du code.  
  
-   [Guide pratique pour ajouter des diagrammes de classes aux projets (Concepteur de classes)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)  
  
#### <a name="summary-strengths-of-class-diagrams"></a>Résumé : atouts des diagrammes de classes  
 Les diagrammes de classes vous permettent de définir :  
  
-   Un glossaire commun des termes à utiliser pour étudier les besoins des utilisateurs et les entités qui participent au système. Consultez la page [modéliser les besoins des utilisateurs](../modeling/model-user-requirements.md).  
  
-   Les types qui sont utilisés par des parties du système, notamment les composants, indépendamment de leur implémentation. Consultez la page [modèle d’architecture de votre application](../modeling/model-your-app-s-architecture.md).  
  
-   Les relations, telles que les dépendances, entre les types. Par exemple, vous pouvez montrer qu’un type peut être associé à plusieurs instances d’un autre type.  
  
#### <a name="relationship-to-other-diagrams"></a>Relation aux autres diagrammes  
  
|**Diagramme**|**Description**|  
|-----------------|---------------------|  
|Diagramme de dépendances|Définit l’architecture logique du système relative aux classes.<br /><br /> Utiliser la validation de dépendance pour vous assurer que le code reste cohérent avec la conception.<br /><br /> Reportez-vous à :<br /><br /> -   [Créer des diagrammes de dépendance à partir de votre code.](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Diagrammes de dépendance : référence](../modeling/layer-diagrams-reference.md)<br />-   [Diagrammes de dépendance : instructions](../modeling/layer-diagrams-guidelines.md)<br />-   [Valider le code avec des diagrammes de dépendance](../modeling/validate-code-with-layer-diagrams.md)|  
|Carte de code|Permet de visualiser l’organisation et les relations dans le code existant.<br /><br /> Pour identifier les classes, leurs relations et leurs méthodes, créez une carte de code qui montre ces éléments.<br /><br /> Reportez-vous à :<br /><br /> -   [Mapper les dépendances dans vos solutions](../modeling/map-dependencies-across-your-solutions.md)|  
  
###  <a name="a-namedescribelayersa-describe-the-logical-architecture-dependency-diagrams"></a><a name="DescribeLayers"></a>Décrire l’Architecture logique : diagrammes de dépendance  
 Diagrammes de dépendance décrivent l’architecture logique d’un système en organisant les artefacts de votre solution en groupes abstraits, ou *couches*. Les artefacts peuvent correspondre à beaucoup de choses, notamment des espaces de noms, des projets, des classes, des méthodes, etc. Les couches représentent et décrivent les rôles ou les tâches que les artefacts exécutent dans le système. Vous pouvez également inclure la validation de couche dans votre build et des opérations d’archivage pour vous assurer que le code reste cohérent avec sa conception.  
  
 Pour conserver un code cohérent avec la conception, Dinner Now et Lucerne utilisent le diagramme de dépendances suivantes pour valider leur code telle qu’elle évolue :  
  
 ![Diagramme de dépendances de système de paiement intégré](../modeling/media/layer_integrated_dnlucerne.png "Layer_Integrated_DNLucerne")  
  
 **Diagramme des dépendances de Dinner Now intégré à Lucerne**  
  
 Les couches de ce diagramme sont liées aux artefacts de solution Dinner Now et Lucerne correspondants. Par exemple, la couche Business est liée à l’espace de noms DinnerNow.Business et à ses membres, qui incluent maintenant la classe PaymentApprover. La couche Resource Access est liée à l’espace de noms DinnerNow.Data. Les flèches, ou *dépendances*, indiquent que seule la couche Business peut utiliser la fonctionnalité dans la couche Resource Access. Quand les équipes mettent à jour leur code, une validation de couche est exécutée régulièrement pour détecter les conflits dès qu’ils se produisent et permettre aux équipes de les résoudre rapidement.  
  
 Les équipes travaillent ensemble pour intégrer et tester progressivement les deux systèmes. Elles vérifient d’abord que PaymentApprover et le reste du système Dinner Now fonctionnent correctement ensemble avant de s’occuper du code PaymentProcessing.  
  
 La carte de code suivante montre les nouveaux appels entre Dinner Now et PaymentApprover :  
  
 ![Graphique de dépendance mis à jour avec système intégré](../modeling/media/depgraph_intsystem.png "DepGraph_IntSystem")  
  
 **Carte de code avec les appels de méthode mis à jour**  
  
 Après avoir vérifié que le système fonctionne comme prévu, Dinner Now commente le code PaymentProcessing. Les rapports de validation de couche sont satisfaisants et la carte de code obtenue indique qu’il n’existe plus aucune dépendance PaymentProcessing :  
  
 ![Graphique de dépendance sans PaymentProcessing](../modeling/media/depgraph_nomore.png "DepGraph_NoMore")  
  
 **Carte de code sans PaymentProcessing**  
  
#### <a name="drawing-a-dependency-diagram"></a>Dessin d’un diagramme de dépendance  
 Un diagramme de dépendances présente les principales fonctionnalités suivantes :  
  
-   Des*couches* décrivent des groupes logiques d’artefacts.  
  
-   Un *lien* est une association entre une couche et un artefact.  
  
     Pour créer des couches à partir d’artefacts, faites glisser des éléments depuis l’Explorateur de solutions, des cartes de code, de l’affichage de classes ou de l’Explorateur d’objets. Pour dessiner de nouvelles couches et les lier aux artefacts, utilisez la boîte à outils, ou cliquez avec le bouton droit sur la surface du diagramme pour créer les couches, puis faites glisser des éléments vers ces couches.  
  
     Le nombre indiqué sur une couche représente le nombre d’artefacts liés à cette couche. Ces artefacts peuvent correspondre à des espaces de noms, des projets, des classes, des méthodes, etc. Quand vous analysez le nombre d’artefacts sur une couche, tenez compte des points suivants :  
  
    -   Si une couche est liée à un artefact contenant d'autres artefacts, mais n'est pas directement liée à ces autres artefacts, le nombre représentera uniquement les artefacts auxquels elle est directement liée. Toutefois, les autres artefacts sont inclus dans l'analyse pendant la validation de couche.  
  
         Par exemple, si une couche est liée à un espace de noms unique, le nombre d'artefacts liés est égal à 1, même si l'espace de noms contient des classes. Si la couche a également des liens vers chaque classe de l'espace de noms, le nombre comprendra les classes liées.  
  
    -   Si une couche contient d'autres couches liées à des artefacts, la couche du conteneur est également liée à ces artefacts, même si le nombre indiqué sur la couche du conteneur ne comprend pas ces artefacts.  
  
     Pour voir les artefacts liés à une couche, avec le bouton droit de la dépendance, puis cliquez sur **afficher les liens** ouvrir **Explorateur de couches**.  
  
-   Une *dépendance* indique qu’une couche peut utiliser la fonctionnalité d’une autre couche, mais pas l’inverse. Une *dépendance bidirectionnelle* indique qu’une couche peut utiliser la fonctionnalité d’une autre couche, et vice versa.  
  
     Pour afficher les dépendances existantes sur le diagramme de dépendances, cliquez sur la surface du diagramme, puis cliquez sur **générer des dépendances**. Pour décrire les dépendances prévues, dessinez-en de nouvelles.  
  
 Reportez-vous à :  
  
-   [Créer des diagrammes de dépendance à partir de votre code.](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Diagrammes de dépendance : référence](../modeling/layer-diagrams-reference.md)  
  
-   [Diagrammes de dépendance : instructions](../modeling/layer-diagrams-guidelines.md)  
  
-   [Valider le code avec des diagrammes de dépendance](../modeling/validate-code-with-layer-diagrams.md)  
  
#### <a name="summary-strengths-of-dependency-diagrams"></a>Résumé : Atouts des diagrammes de dépendance  
 Diagrammes de dépendance vous aident à :  
  
-   décrire l’architecture logique d’un système selon les fonctionnalités de ses artefacts ;  
  
-   vérifier que le code en cours de développement est conforme à la conception spécifiée.  
  
#### <a name="relationship-to-other-diagrams"></a>Relation aux autres diagrammes  
  
|**Diagramme**|**Description**|  
|-----------------|---------------------|  
|Carte de code|Permet de visualiser l’organisation et les relations dans le code existant.<br /><br /> Pour créer des couches, générez une carte de code, puis regroupez les éléments sur la carte en tant que couches potentielles. Faites glisser les groupes à partir de la carte vers le diagramme de dépendance.<br /><br /> Reportez-vous à :<br /><br /> -   [Mapper les dépendances dans vos solutions](../modeling/map-dependencies-across-your-solutions.md)<br />-   [Parcourir et réorganiser des cartes de code](../modeling/browse-and-rearrange-code-maps.md)|  
  
## <a name="external-resources"></a>Ressources externes  
  
|**Catégorie**|**Liens**|  
|------------------|---------------|  
|**Forums**|-   [Visual Studio Visualization s’outils de modélisation](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio Visualization se Modeling SDK (outils DSL)](http://go.microsoft.com/fwlink/?LinkId=184721)|  
  
## <a name="see-also"></a>Voir aussi  
 [Visualiser le code](../modeling/visualize-code.md)   
 [Utiliser des modèles dans votre processus de développement](../modeling/use-models-in-your-development-process.md)   
 [Utiliser des modèles dans le développement Agile](http://msdn.microsoft.com/en-us/592ac27c-3d3e-454a-9c38-b76658ed137f)   
 [Valider votre système pendant le développement](../modeling/validate-your-system-during-development.md)   

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
 
