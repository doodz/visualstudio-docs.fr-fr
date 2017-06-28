---
title: "Visualisation et l’affichage des données | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], viewing data
- debugging [Debugging SDK], visualizing data
ms.assetid: 699dd0f5-7569-40b3-ade6-d0fe53e832bc
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 3f2317abd4bfaf6ebf8151812cf15541a1c94ecf
ms.lasthandoff: 04/05/2017

---
# <a name="visualizing-and-viewing-data"></a>Visualisation et l’affichage des données
Visualiseurs de types et les visionneuses personnalisées présentent les données de façon significative rapidement à un développeur. L’évaluateur d’expression (EE) peut prendre en charge les visualiseurs de types de tiers ainsi que fournir ses propres visionneuses personnalisées.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Détermine le nombre de visualiseurs de types et les visionneuses personnalisées sont associées avec le type d’objet en appelant le [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) (méthode). Si le visualiseur d’au moins un type ou la visionneuse personnalisée est disponible, Visual Studio appelle le [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) méthode pour récupérer une liste de ces visualiseurs et les visionneuses (en fait, une liste de `CLSID`s qui implémentent les visualiseurs et les visionneuses) et les affiche à l’utilisateur.  
  
## <a name="supporting-type-visualizers"></a>Prise en charge les visualiseurs de types  
 Il existe un nombre d’interfaces qui le EE doit implémenter pour prendre en charge les visualiseurs de types. Ces interfaces peuvent être décomposées en deux grandes catégories : ceux qui liste les visualiseurs de types et ceux qui accèdent aux données de la propriété.  
  
### <a name="listing-type-visualizers"></a>Visualiseurs de types de liste  
 Prend en charge de la EE répertoriant les visualiseurs de types dans son implémentation de `IDebugProperty3::GetCustomViewerCount` et `IDebugProperty3::GetCustomViewerList`. Ces méthodes passent l’appel aux méthodes correspondantes [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) et [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md).  
  
 Le [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) est obtenu en appelant [CreateVisualizerService](../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md). Cette méthode requiert le [IDebugBinder3](../../extensibility/debugger/reference/idebugbinder3.md) interface, qui est obtenue à partir de la [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) interface passé à [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md). `IEEVisualizerServiceProvider::CreateVisualizerService`requiert également le [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) et [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) les interfaces qui ont été passés à `IDebugParsedExpression::EvaluateSync`. L’interface final requise pour créer le `IEEVisualizerService` interface est le [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md) interface, ce qui met en œuvre le Java EE. Cette interface permet des modifications à apporter à la propriété qui est visualisée. Toutes les données de propriété est encapsulé dans un [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) interface, qui est également implémentée par le Java EE.  
  
### <a name="accessing-property-data"></a>L’accès aux données de propriété  
 L’accès aux données de la propriété est effectuée via le [IPropertyProxyEESide](../../extensibility/debugger/reference/ipropertyproxyeeside.md) interface. Pour obtenir cette interface, Visual Studio appelle [QueryInterface](/cpp/atl/queryinterface) sur l’objet de propriété à obtenir le [IPropertyProxyProvider](../../extensibility/debugger/reference/ipropertyproxyprovider.md) interface (implémentée sur le même objet qui implémente le [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) interface), puis appelle la [GetPropertyProxy](../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) méthode pour obtenir le `IPropertyProxyEESide` interface.  
  
 Toutes les données passées dans et hors de la `IPropertyProxyEESide` interface est encapsulé dans le [IEEDataStorage](../../extensibility/debugger/reference/ieedatastorage.md) interface. Cette interface représente un tableau d’octets et est implémentée par Visual Studio et le Java EE. Lorsque les données d’une propriété doit être modifiée, Visual Studio crée un `IEEDataStorage` objet contenant les nouvelles données et les appels [CreateReplacementObject](../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) avec cet objet de données afin d’obtenir un nouveau `IEEDataStorage` objet qui, à son tour, est passé à [InPlaceUpdateObject](../../extensibility/debugger/reference/ipropertyproxyeeside-inplaceupdateobject.md) pour mettre à jour les données de la propriété. `IPropertyProxyEESide::CreateReplacementObject`permet la EE d’instancier sa propre classe qui implémente le `IEEDataStorage` interface.  
  
## <a name="supporting-custom-viewers"></a>Prise en charge des visionneuses personnalisées  
 L’indicateur `DBG_ATTRIB_VALUE_CUSTOM_VIEWER` est défini dans le `dwAttrib` champ le [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md) structure (retourné par un appel à [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)) pour indiquer que l’objet a une visionneuse personnalisée associée. Lorsque cet indicateur est défini, Visual Studio obtient les [IDebugProperty3](../../extensibility/debugger/reference/idebugproperty3.md) de l’interface à partir de la [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) à l’aide de l’interface [QueryInterface](/cpp/atl/queryinterface).  
  
 Si l’utilisateur sélectionne une visionneuse personnalisée, Visual Studio instancie la visionneuse personnalisée à l’aide de la visionneuse `CLSID` fourni par le `IDebugProperty3::GetCustomViewerList` (méthode). Visual Studio appelle ensuite [une valeur d’affichage](../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md) pour afficher la valeur à l’utilisateur.  
  
 Normalement, `IDebugCustomViewer::DisplayValue` présente une vue en lecture seule des données. Pour autoriser les modifications apportées aux données, le EE doit implémenter une interface personnalisée qui prend en charge les données de modification sur un objet de propriété. Le `IDebugCustomViewer::DisplayValue` méthode utilise cette interface personnalisée pour prendre en charge la modification des données. La méthode recherche l’interface personnalisée le `IDebugProperty2` interface transmis en tant que le `pDebugProperty` argument.  
  
## <a name="supporting-both-type-visualizers-and-custom-viewers"></a>Prise en charge de Type visualiseurs et les visionneuses personnalisées  
 Un EE peut prendre en charge les visualiseurs de types et des visionneuses personnalisées dans le [GetCustomViewerCount](../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) et [GetCustomViewerList](../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) méthodes. Tout d’abord, le EE ajoute le nombre de visionneuses personnalisées, il fournit à la valeur retournée par la [GetCustomViewerCount](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) (méthode). En second lieu, le EE ajoute le `CLSID`s de ses propres visionneuses personnalisées pour la liste retournée par la [GetCustomViewerList](../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md) (méthode).  
  
## <a name="see-also"></a>Voir aussi  
 [Tâches de débogage](../../extensibility/debugger/debugging-tasks.md)   
 [Visualiseur de type et visionneuse personnalisée](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)