---
title: "Comment : ajouter des commandes aux menus contextuels | Documents Microsoft"
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
- Office menus, creating
- Office development in Visual Studio, context menus
ms.assetid: 9a848817-db11-4294-8f6f-9181ab87aadd
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 40b2bbb7c7b86665790a06feed288b0dd37272df
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-commands-to-shortcut-menus"></a>Comment : ajouter des commandes à des menus contextuels
  Cette rubrique montre comment ajouter des commandes à un menu contextuel dans une application Office en utilisant un complément VSTO.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
### <a name="to-add-commands-to-shortcut-menus-in-office"></a>Pour ajouter des commandes à des menus contextuels dans Office  
  
1.  Ajoutez un élément **Ribbon XML** à un projet au niveau du document ou de complément VSTO. Pour plus d'informations, consultez [How to: Get Started Customizing the Ribbon](../vsto/how-to-get-started-customizing-the-ribbon.md). Vers l'avant  
  
2.  Dans l’**Explouateur de solutions**, sélectionnez **ThisAddin.cs** ou **ThisAddin.vb**.  
  
3.  Dans la barre de menus, sélectionnez **Afficher**, **Code**.  
  
     Le fichier de classe **ThisAddin** s’ouvre dans l’éditeur de code.  
  
4.  Ajoutez le code suivant à la classe **ThisAddin** . Ce code substitue la méthode CreateRibbonExtensibilityObject et retourne la classe Ribbon XML à l’application Office.  
  
     [!code-csharp[Trin_WordAddIn_Menus#1](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/thisaddin.cs#1)]
     [!code-vb[Trin_WordAddIn_Menus#1](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/thisaddin.vb#1)]  
  
5.  Dans l’ **Explorateur de solutions**, sélectionnez le fichier XML de ruban. Par défaut, le fichier XML de ruban se nomme Ribbon1.xml.  
  
6.  Dans la barre de menus, sélectionnez **Afficher**, **Code**.  
  
     Le fichier XML de ruban s’ouvre dans l’éditeur de code.  
  
7.  Dans l’éditeur de code, ajoutez le code XML qui décrit le menu contextuel et le contrôle à ajouter au menu contextuel.  
  
     L’exemple suivant ajoute un bouton, un menu et un contrôle de galerie au menu contextuel d’un document Word. L’ID du contrôle de ce menu contextuel est ContextMenuText. Pour obtenir la liste complète de contrôle Office 2010 ID, consultez [fichiers d’aide Office 2010 : identificateurs de contrôle d’Interface utilisateur Office Fluent](http://go.microsoft.com/fwlink/?LinkID=181052).  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?>  
    <customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui">  
      <contextMenus>  
        <contextMenu idMso="ContextMenuText">  
          <button id="MyButton" label="My Button" insertBeforeMso="HyperlinkInsert" onAction="GetButtonID" />  
          <menu id="MySubMenu" label="My Submenu" >  
            <button id="MyButton2" label="Button on submenu" />  
          </menu>  
          <gallery id="galleryOne" label="My Gallery">  
            <item id="item1" imageMso="HappyFace" />  
            <item id="item2" imageMso="HappyFace" />  
            <item id="item3" imageMso="HappyFace" />  
            <item id="item4" imageMso="HappyFace" />  
          </gallery>  
        </contextMenu>  
      </contextMenus>  
    </customUI>  
    ```  
  
8.  Dans l’ **Explorateur de solutions**, choisissez **MyRibbon.cs** ou **MyRibbon.vb**.  
  
9. Ajoutez la méthode de rappel à la classe `Ribbon1` pour chaque contrôle à gérer.  
  
     La méthode de rappel suivante gère le bouton **Mon bouton** . Ce code ajoute une chaîne au document actif à l’emplacement actuel du curseur.  
  
     [!code-vb[Trin_WordAddIn_Menus#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/ribbon1.vb#2)]
     [!code-csharp[Trin_WordAddIn_Menus#2](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/ribbon1.cs#2)]  
  
## <a name="see-also"></a>Voir aussi  
 [Personnalisation de l’interface utilisateur Office](../vsto/office-ui-customization.md)   
 [Procédure pas à pas : Création de Menus contextuels pour les signets](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)   
 [Paramètres optionnels dans les Solutions Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Personnalisation des Menus contextuels dans Office 2010](http://go.microsoft.com/fwlink/?LinkId=182186)  
  
  