---
title: IDebugObject::SetValue |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::SetValue
helpviewer_keywords:
- IDebugObject::SetValue method
ms.assetid: d652e09c-cdc1-4519-8116-d7c743f5679b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f1b78a4513aab8a9c4d2c539a592799dffdcea53
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49850966"
---
# <a name="idebugobjectsetvalue"></a>IDebugObject::SetValue
设置对象的值从一系列连续的字节数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetValue(   
   BYTE* pValue,  
   UINT  nSize  
);  
```  
  
```csharp  
int SetValue(  
   byte[] pValue,   
   uint   nSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pValue`  
 [in]一个表示新值的字节数组。  
  
 `nSize`  
 [in]以字节为单位的值的大小。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 数组中的值复制到此[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象，并将任何现有值替换。 新值的大小可大于或小于现有值。 这`IDebugObject`不能为 null 引用。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)