---
title: IDebugComPlusSymbolProvider::UnloadSymbols |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- UnloadSymbols
- IDebugComPlusSymbolProvider::UnloadSymbols
ms.assetid: 53e3ddc1-ab47-4097-8fef-b26e5504b37a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7d24ade16c99377da46267305251b3be688048a2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49896115"
---
# <a name="idebugcomplussymbolproviderunloadsymbols"></a>IDebugComPlusSymbolProvider::UnloadSymbols
卸载从内存指定的模块的调试符号。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT UnloadSymbols(  
   ULONG32 ulAppDomainID,  
   GUID    guidModule  
);  
```  
  
```csharp  
int UnloadSymbols(  
   uint ulAppDomainID,  
   Guid guidModule  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ulAppDomainID`  
 [in]应用程序域的标识符。  
  
 `guidModule`  
 [in]该模块的唯一标识符。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于**CDebugSymbolProvider**对象，它公开[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)接口。  
  
```cpp  
HRESULT CDebugSymbolProvider::UnloadSymbols(  
    ULONG32 ulAppDomainID,  
    GUID guidModule  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pmodule;  
    Module_ID idModule(ulAppDomainID, guidModule);  
  
    METHOD_ENTRY( CDebugSymbolProvider::UnloadSymbols );  
  
#if DEBUG  
  
    DebugVerifyModules();  
#endif  
  
    IfFailGo( GetModule( idModule, &pmodule ) );  
  
#if DEBUG  
  
    DebugVerifyModules();  
#endif  
  
    RemoveModule( pmodule );  
    pmodule->Cleanup();  
  
Error:  
#if DEBUG  
  
    DebugVerifyModules();  
#endif  
  
    METHOD_EXIT( CDebugSymbolProvider::UnloadSymbols, hr );  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)