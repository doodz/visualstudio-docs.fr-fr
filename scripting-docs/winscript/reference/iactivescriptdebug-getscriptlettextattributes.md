---
title: "IActiveScriptDebug::GetScriptletTextAttributes | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptDebug.GetScriptletTextAttributes
apilocation: jscript.dll
helpviewer_keywords: 
  - "IActiveScriptDebug::GetScriptletTextAttributes"
ms.assetid: b3990d86-5fdf-4c9f-9678-3f4b808c7ca8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptDebug::GetScriptletTextAttributes
Retourne les attributs de texte pour un scriptlet arbitraire.  
  
## Syntaxe  
  
```  
HRESULT GetScriptletTextAttributes(  
   LPCOLESTR          pstrCode,  
   ULONG              uNumCodeChars,  
   LPCOLESTR          pstrDelimiter,  
   DWORD              dwFlags,  
   SOURCE_TEXT_ATTR*  pattr  
);  
```  
  
#### Paramètres  
 `pstrCode`  
 \[in\]  le texte de scriptlet.  Cette chaîne n'a pas besoin d'être null terminée.  
  
 `uNumCodeChars`  
 \[in\]  Le nombre de caractères du texte de scriptlet.  
  
 `pstrDelimiter`  
 \[in\]  Adresse du délimiteur de fin de scriptlet.  Lorsque `pstrCode` est analysé d'un flux de texte, l'hôte utilise généralement un séparateur, par exemple deux guillemets simples \('\), pour détecter la fin du scriptlet.  Ce paramètre spécifie que le séparateur qui l'hôte utilisé, ce qui permet au moteur de script pour fournir du prétraitement primitive conditionnel \(par exemple, en remplaçant un guillemet simple \[« \] par deux guillemets simples pour l " utilisation comme séparateur\).  Exactement comment \(et\) si le moteur de script utilise ces informations dépendent du moteur de script.  Définissez ce paramètre POUR ANNULER si l'hôte n'avait pas l'habitude un séparateur pour marquer la fin du scriptlet.  
  
 `dwFlags`  
 \[in\]  Balises associées au scriptlet.  Peut être une combinaison de ces valeurs :  
  
|Constante|Valeur|Description|  
|---------------|------------|-----------------|  
|GETATTRTYPE\_DEPSCAN|0x0001|Indique que les identificateurs et les opérateurs de débogage doivent être marqués avec les indicateurs de SOURCETEXT\_ATTR\_IDENTIFIER et de SOURCETEXT\_ATTR\_MEMBERLOOKUP, respectivement.|  
|GETATTRFLAG\_THIS|0x0100|Indique que l'identificateur de l'objet actuel doit être marqué avec la balise de SOURCETEXT\_ATTR\_THIS.|  
|GETATTRFLAG\_HUMANTEXT|0x8000|Indique que le contenu de la chaîne et le texte de commentaire doivent être marqués avec la balise de SOURCETEXT\_ATTR\_HUMANTEXT.|  
  
 `pattr`  
 \[in, out\]  mémoire tampon pour contenir les attributs retournés.  
  
## Valeur de retour  
 La méthode retourne `HRESULT`.  Les valeurs possibles incluent, mais ne sont pas limitées à, celles dans le tableau suivant.  
  
|Valeur|Description|  
|------------|-----------------|  
|`S_OK`|La méthode a réussi.|  
  
## Notes  
 Un hôte intelligent qui implémente l'interface d' `IDebugDocumentText` peut utiliser cette méthode pour déléguer des appels à la méthode d' `IDebugDocumentText::GetText` .  
  
 Cet appel est fourni car les scriptlets ont tendance à être des expressions et peuvent avoir une syntaxe différente qu'un bloc de script.  Si elles ont la même syntaxe, l'implémentation de cette méthode est identique à l'implémentation de la méthode d' `GetScriptTextAttributes` .  
  
## Voir aussi  
 [IActiveScriptDebug, interface](../../winscript/reference/iactivescriptdebug-interface.md)   
 [IActiveScriptDebug::GetScriptTextAttributes](../../winscript/reference/iactivescriptdebug-getscripttextattributes.md)   
 [IDebugDocumentText, interface](../../winscript/reference/idebugdocumenttext-interface.md)   
 [IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)   
 [SOURCE\_TEXT\_ATTR, énumération](../../winscript/reference/source-text-attr-enumeration.md)