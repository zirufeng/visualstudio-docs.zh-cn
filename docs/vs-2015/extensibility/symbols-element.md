---
title: 符号元素 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Symbols element (VSCT XML schema)
- VSCT XML schema elements, Symbols
ms.assetid: 1cda43d8-42a5-4b1b-a3c8-cf0401c3202f
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6b9bccb3874d5b85a8a69288e2bf44adb14b5b3f
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51783236"
---
# <a name="symbols-element"></a>Symbols 元素
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

定义 Guid 并由其他 VSCT 元素的 Id。 对于非托管代码中，此信息通常来自所指定的标头文件[Extern 元素](../extensibility/extern-element.md)。 托管代码使用符号元素定义此信息的子元素。  
  
 如果从现有.cto 文件创建.vsct 文件，将作为符号元素的子级生成符号。 有关详细信息，请参阅[如何： 创建。从现有的 Vsct 文件。首席技术官文件](../misc/how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file.md)。  
  
 不要将符号元素与相混淆[定义元素](../extensibility/define-element.md)，用于定义由预处理器使用的名称 / 值对。  
  
## <a name="syntax"></a>语法  
  
```  
<Symbols>  
  <GuidSymbol>... </GuidSymbol>  
  <GuidSymbol>... </GuidSymbol>  
</Symbols>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|无||  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|GuidSymbol|定义在 GUID 符号。 GuidSymbol 有两个必需的属性： 名称和值。 名称为符号的名称，值为 GUID 字符串形式的值。<br /><br /> 例如：\<GuidSymbol 名称 ="guidVsPackage1Pkg"value ="{c5f54698-101a-4846-84d3-dc748f9cd848}"/ >|  
|IDSymbol|定义的符号。 IDSymbol 有两个必需的属性： 名称和值。 名称为符号的名称，值为字符串形式的符号的值。<br /><br /> 例如：\<IDSymbol 名称 ="MyMenuGroup"value ="0x1020"/ >|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[CommandTable 元素](../extensibility/commandtable-element.md)|.Vsct 文件的根元素。|  
  
## <a name="example"></a>示例  
  
```  
<Symbols>  
  <GuidSymbol name="guidVsPackage1Pkg" value="{c5f54698-101a-4846-84d3-dc748f9cd848}" />  
  <GuidSymbol name="guidVsPackage1CmdSet" value="{cb9dfd7f-2fcc-4a3e-aae8-f7fe30b1cfac}">  
    <IDSymbol name="MyMenuGroup" value="0x1020" />  
    <IDSymbol name="cmdidMyCommand" value="0x0100" />  
    <IDSymbol name="cmdidMyTool" value="0x0101" />  
  </GuidSymbol>  
</Symbols>  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令表格 (.Vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

