---
title: IDebugDocumentContext2 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugDocumentContext2
helpviewer_keywords:
- IDebugDocumentContext2
ms.assetid: 2a446c71-8100-4c09-a1cc-fd446bd74030
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73165d2ed2b8edf1d39232dbc667e583b4f2bf50
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51762944"
---
# <a name="idebugdocumentcontext2"></a>IDebugDocumentContext2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此接口表示源文件文档中的位置。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugDocumentContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 调试引擎 (DE) 实现此接口作为源代码级别调试的支持的一部分。 除了在源代码中位置，此接口提供了用于比较上下文和源代码文档中导航方法。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 方法在多个接口，通常最[GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)并[GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)接口，返回此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugDocumentContext2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)|获取包含此文档上下文中的文档。|  
|[GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)|获取包含此文档上下文中的文档的可显示名称。|  
|[EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)|检索与此文档上下文关联的所有代码上下文的列表。|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugdocumentcontext2-getlanguageinfo.md)|获取与此文档上下文关联的语言。|  
|[GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|获取此文档上下文中的文件语句范围。|  
|[GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)|获取此文档上下文中的文件源范围。|  
|[Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)|比较此文档上下文到给定数组的文档上下文。|  
|[Seek](../../../extensibility/debugger/reference/idebugdocumentcontext2-seek.md)|按给定数量的语句或行移动文档上下文。|  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)

