---
title: 线程 |Microsoft Docs
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
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fdb69d6d489d72bea7611c807337e7429fd94ad9
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51744253"
---
# <a name="threads"></a>线程
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

在调试器体系结构，方面**线程**:  
  
-   是计算的基本单位。 线程按顺序执行其上下文中的单一调用堆栈，将从一种代码上下文移到下一步的说明。  
  
-   可以标识本身和它运行在中，可以将名为、 挂起，并且恢复的计划。 线程还可以枚举其关联的堆栈帧，并在某些情况下可以移动到另一个堆栈帧。 给定堆栈帧上下文内的，线程可以返回其关联的逻辑线程，如果有的话。 线程都具有属性，例如挂起计数，可以显示在 IDE 的线程窗口中。  
  
-   为由[IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md)接口，通常创建的调试引擎 (DE) 或虚拟机，因此执行程序。  
  
## <a name="see-also"></a>请参阅  
 [程序](../../extensibility/debugger/programs.md)   
 [堆栈帧](../../extensibility/debugger/stack-frames.md)   
 [调试引擎](../../extensibility/debugger/debug-engine.md)   
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)   
 [会话调试管理器](../../extensibility/debugger/session-debug-manager.md)

