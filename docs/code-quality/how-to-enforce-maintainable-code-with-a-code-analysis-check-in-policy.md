---
title: "Comment : appliquer du Code facile à maintenir avec une stratégie d’archivage de l’analyse du Code | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code analysis, check-in policies
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 39d9697c7d6a216c08e34eb19287d22a76d67a55
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-enforce-maintainable-code-with-a-code-analysis-check-in-policy"></a>Comment : appliquer du code facile à maintenir avec une stratégie d’archivage de l’analyse du code
Les développeurs peuvent utiliser l’outil de métrique du Code pour mesurer la complexité et la facilité de maintenance de leur code, mais ils ne peuvent pas appeler la métrique du code dans le cadre d’une stratégie d’archivage. Toutefois, une équipe peut activer des règles d’analyse du Code pour vérifier la conformité de leur code avec les normes de la métrique du Code et appliquent les règles via des stratégies d’archivage. Pour plus d’informations sur la métrique du code, consultez la [les valeurs de métrique de Code](../code-quality/code-metrics-values.md).  
  
 Les développeurs peuvent activer la profondeur d’héritage, couplage de classe, indice de maintenabilité et règles de complexité appliquer du code facile à gérer via des stratégies d’archivage de l’analyse du Code. Les quatre de ces règles sont trouvent sous la catégorie « Règles de facilité de maintenance » dans l’éditeur de stratégie d’analyse du Code.  
  
 Les administrateurs de la version de contrôle pour [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] pouvez ajouter des règles de facilité de gestion d’analyse du Code aux exigences de stratégie d’archivage. Ces archivage stratégies exigent des développeurs exécuter l’analyse du Code basé sur ces modifications de la règle avant d’initier un archivage.  
  
### <a name="to-open-the-code-analysis-policy-editor"></a>Pour ouvrir l’éditeur de stratégie d’analyse de Code  
  
1.  Dans **Team Explorer**, cliquez sur le projet d’équipe, cliquez sur **paramètres du projet d’équipe**, puis cliquez sur **contrôle de code Source**.  
  
     Le **contrôle de code Source** boîte de dialogue s’affiche.  
  
2.  Sur le **stratégie d’archivage** onglet, puis cliquez sur **ajouter**.  
  
     Le **ajouter la stratégie d’archivage** boîte de dialogue s’affiche.  
  
3.  Dans le **stratégie d’archivage** liste, sélectionnez le **l’analyse du Code** case à cocher, puis cliquez sur **OK**.  
  
     Le **éditeur de stratégie de Code Analysis** boîte de dialogue s’affiche.  
  
### <a name="to-enable-code-analysis-maintainability-rules"></a>Pour activer les règles d’analyse du Code de facilité de maintenance  
  
1.  Dans le **éditeur de stratégie de Code Analysis** boîte de dialogue **paramètres de règle**, développez le **règles de maintenance** nœud.  
  
2.  Activez les cases à cocher pour les règles suivantes :  
  
    -   Profondeur d’héritage : **CA1501 AvoidExcessiveInheritance** -seuil : avertissement à plus de 5 niveaux  
  
    -   Complexité : **CA1502 AvoidExcessiveComplexity** -seuil : avertissement à plus de 25  
  
    -   Indice de maintenabilité : **CA1505 AvoidUnmaintainableCode** -seuil : avertissement à moins de 20  
  
    -   COUPLAGE de classe : **CA1506 AvoidExcessiveClassCoupling** -seuil : avertissement à plus de 80 pour une classe et plus de 30 pour une méthode  
  
    -   En outre, si vous souhaitez une violation de règle empêche une génération, sélectionnez le **traiter un avertissement comme une erreur** case à cocher en regard de la description de la règle.  
  
3.  Cliquez sur **OK**. La nouvelle stratégie d’archivage s’applique désormais aux archivages ultérieurs.  
  
## <a name="see-also"></a>Voir aussi  
 [Valeurs de métrique de code](../code-quality/code-metrics-values.md)   
 [Création et utilisation de stratégies d’archivage de l’analyse du code](../code-quality/creating-and-using-code-analysis-check-in-policies.md)