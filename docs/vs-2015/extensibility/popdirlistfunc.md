---
title: POPDIRLISTFUNC |Microsoft Docs
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
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7b1361350b5a0c349ec8bd95a877c4fbaf75eafc
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51802748"
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

这是一个回调函数提供给[SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)函数更新目录和 （可选） 要找出哪些是受源代码管理的文件名称的集合。  
  
 `POPDIRLISTFUNC`应仅对这些目录和文件的名称调用回调 (在列表中提供给`SccPopulateDirList`函数)，实际上是在源代码管理下。  
  
## <a name="signature"></a>签名  
  
```cpp#  
typedef BOOL (*POPDIRLISTFUNC)(  
   LPVOID pvCallerData,  
   BOOL bFolder,  
   LPCSTR lpDirectoryOrFileName  
);  
```  
  
## <a name="parameters"></a>参数  
 pvCallerData  
 [in]用户值赋予[SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)。  
  
 bFolder  
 [in]`TRUE`如果中的名称`lpDirectoryOrFileName`是一个目录中; 否则，名称是一个文件名。  
  
 lpDirectoryOrFileName  
 [in]向源代码管理下的目录或文件名称的完整的本地路径。  
  
## <a name="return-value"></a>返回值  
 IDE 将返回相应的错误代码：  
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|继续进行处理。|  
|SCC_I_OPERATIONCANCELED|停止处理。|  
|SCC_E_xxx|任何适当的源控制错误应停止处理。|  
  
## <a name="remarks"></a>备注  
 如果`fOptions`的参数`SccPopulateDirList`函数包含`SCC_PDL_INCLUDEFILES`标志，则列表将可能包含文件的名称，以及目录名称。  
  
## <a name="see-also"></a>请参阅  
 [通过 IDE 实现的回调函数](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)   
 [错误代码](../extensibility/error-codes.md)

