---
title: "Cr&#233;ation d’une fen&#234;tre d’outil d’instances multiples | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "multiple"
  - "fenêtres Outil"
ms.assetid: 4a7872f1-acc9-4f43-8932-5a526b36adea
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# Cr&#233;ation d’une fen&#234;tre d’outil d’instances multiples
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Vous pouvez programmer une fenêtre outil afin que plusieurs instances de ce type peuvent être ouverts simultanément. Par défaut, les fenêtres Outil peuvent ouvrir qu’une seule instance.  
  
 Lorsque vous utilisez une fenêtre d’outil d’instances multiples, vous pouvez afficher plusieurs sources connexes d’informations en même temps. Par exemple, vous pouvez placer un multiligne <xref:System.Windows.Forms.TextBox> contrôle dans une fenêtre d’outil d’instances multiples de sorte que plusieurs extraits de code sont accessibles simultanément pendant une session de programmation. Également par exemple, vous pouvez placer un <xref:System.Windows.Forms.DataGrid> contrôle et une liste déroulante de zone dans une fenêtre d’outils multi\-instance afin que plusieurs sources de données en temps réel peuvent être suivis simultanément.  
  
## Création d’une fenêtre d’outil Basic \(uniques\)  
  
1.  Créez un projet nommé **MultiInstanceToolWindow** à l’aide du modèle VSIX et ajouter un modèle d’élément de fenêtre Outil personnalisée nommé **MIToolWindow**.  
  
    > [!NOTE]
    >  Pour plus d’informations sur la création d’une extension avec une fenêtre outil, consultez [Création d'une Extension avec une fenêtre outil](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## Rendre une instance de fenêtre multiples  
  
1.  Ouvrez la **MIToolWindowPackage.cs** de fichiers et recherchez le `ProvideToolWindow` attribut. et le `MultiInstances=true` paramètre, comme indiqué dans l’exemple suivant.  
  
    ```c#  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
        [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
        [ProvideMenuResource("Menus.ctmenu", 1)]  
        [ProvideToolWindow(typeof(MultiInstanceToolWindow.MIToolWindow), MultiInstances = true)]  
        [Guid(MIToolWindowPackageGuids.PackageGuidString)]  
        public sealed class MIToolWindowPackage : Package  
    {. . .}  
    ```  
  
2.  Dans le fichier MIToolWindowCommand.cs, recherchez la méthode ShowToolWindos\(\). Dans cette méthode, appelez la <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> méthode et définissez son `create` indicateur `false` afin qu’il effectue une itération dans les instances existantes de fenêtre outil jusqu'à une disponible `id` est trouvé.  
  
3.  Pour créer une instance de fenêtre outil, appelez le <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> méthode et définissez son `id` à des valeurs disponibles et ses `create` indicateur `true`.  
  
     Par défaut, la valeur de le `id` paramètre de la <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> méthode est `0`. Cela permet une fenêtre outil d’instance unique. Pour plus d’une instance hébergée, chaque instance doit posséder son propre `id`.  
  
4.  Appelez le <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> méthode sur le <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objet qui est retourné par la <xref:Microsoft.VisualStudio.Shell.ToolWindowPane.Frame%2A> propriété de l’instance de fenêtre outil.  
  
5.  Par défaut, le `ShowToolWindow` méthode créé par le modèle d’élément de fenêtre outil crée une fenêtre outil d’instance unique. L’exemple suivant montre comment modifier le `ShowToolWindow` méthode pour créer plusieurs instances.  
  
    ```c#  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        for (int i = 0; i < 10; i++)  
        {  
            ToolWindowPane window = this.package.FindToolWindow(typeof(MIToolWindow), i, false);  
            if (window == null)  
            {  
                // Create the window with the first free ID.   
                window = (ToolWindowPane)this.package.FindToolWindow(typeof(MIToolWindow), i, true);  
                if ((null == window) || (null == window.Frame))  
                {  
                    throw new NotSupportedException("Cannot create tool window");  
                }  
  
            IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
            break;  
            }  
        }  
    }  
    ```