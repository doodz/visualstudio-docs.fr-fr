---
title: "Comment : utiliser par programme des boîtes de dialogue intégrées dans Word | Documents Microsoft"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, Word
ms.assetid: 0c7e4338-dead-4444-868b-3b0212368455
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7dd7d81837699aedd1c6c61d0cb0d9e2e9a64db4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-use-built-in-dialog-boxes-in-word"></a>Comment : utiliser les boîtes de dialogue intégrées dans Word par programmation
  Lorsque vous travaillez avec Microsoft Office Word, voici les heures lorsque vous devez afficher des boîtes de dialogue pour l’entrée d’utilisateur. Vous pouvez créer votre propre, vous souhaiterez également adopter l’approche de l’utilisation des boîtes de dialogue intégrées dans Word, qui sont exposées dans le <xref:Microsoft.Office.Interop.Word.Dialogs> collection de la <xref:Microsoft.Office.Interop.Word.Application> objet. Cela vous donne accès au plus de 200 des boîtes de dialogue intégrées, représentées comme des énumérations.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="displaying-dialog-boxes"></a>Affichage de boîtes de dialogue  
 Pour afficher une boîte de dialogue, utilisez une des valeurs de la <xref:Microsoft.Office.Interop.Word.WdWordDialog> énumération pour créer un <xref:Microsoft.Office.Interop.Word.Dialog> objet qui représente la boîte de dialogue que vous souhaitez afficher. Ensuite, appelez le <xref:Microsoft.Office.Interop.Word.Dialog.Show%2A> méthode de la <xref:Microsoft.Office.Interop.Word.Dialog> objet.  
  
 L’exemple de code suivant montre comment afficher le **ouvrir le fichier** boîte de dialogue. Pour utiliser cet exemple, exécutez-le à partir de la `ThisDocument` ou `ThisAddIn` classe dans votre projet.  
  
 [!code-vb[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#100)]
 [!code-csharp[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#100)]  
  
### <a name="accessing-dialog-box-members-that-are-available-through-late-binding"></a>L’accès aux membres de boîte de dialogue sont disponibles via une liaison tardive  
 Certaines propriétés et méthodes des boîtes de dialogue dans Word sont disponibles uniquement via une liaison tardive. En Visual Basic, projets dans lesquels **Option Strict** est activé, vous devez utiliser la réflexion pour accéder à ces membres. Pour plus d'informations, consultez [Late Binding in Office Solutions](../vsto/late-binding-in-office-solutions.md).  
  
 L’exemple de code suivant montre comment utiliser le **nom** propriété de la **ouvrir le fichier** boîte de dialogue dans Visual Basic projets dans lesquels **Option Strict** est désactivé ou en Visual c# les projets qui ciblent le [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ou [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Pour utiliser cet exemple, exécutez-le à partir de la `ThisDocument` ou `ThisAddIn` classe dans votre projet.  
  
 [!code-vb[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#122)]
 [!code-csharp[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#122)]  
  
 L’exemple de code suivant montre comment utiliser la réflexion pour accéder à la **nom** propriété de la **ouvrir le fichier** boîte de dialogue dans Visual Basic projets dans lesquels **Option Strict** est sur. Pour utiliser cet exemple, exécutez-le à partir de la `ThisDocument` ou `ThisAddIn` classe dans votre projet.  
  
 [!code-vb[Trin_VstcoreWordAutomation#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#102)]  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : utiliser par programme des boîtes de dialogue Word en Mode masqué](../vsto/how-to-programmatically-use-word-dialog-boxes-in-hidden-mode.md)   
 [Vue d’ensemble du modèle d’objet Word](../vsto/word-object-model-overview.md)   
 [Paramètres optionnels dans les Solutions Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Option Strict, instruction](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Réflexion (C#)](/dotnet/csharp/programming-guide/concepts/reflection)  
 [Réflexion (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)  
  
  