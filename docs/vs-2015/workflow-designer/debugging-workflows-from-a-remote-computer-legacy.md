---
title: 调试工作流从远程计算机 （旧版） |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 2b3627b6d62b1f4d237c2f2013d332be56b58fc6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49191571"
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>通过远程计算机调试工作流（旧版）
本主题介绍如何调试使用旧 [!INCLUDE[wf](../includes/wf-md.md)] 生成的旧远程 [!INCLUDE[wfd1](../includes/wfd1-md.md)] 应用程序。 在应用程序需要面向 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 或 [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] 时，请使用旧 [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)]。  
  
 当你安装[!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)]，其中一个组件安装选项是安装[!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)]调试器[!INCLUDE[wf](../includes/wf-md.md)]。 这将安装远程调试组件。 必须在将要进行远程工作流调试的目标计算机上安装这些远程调试组件。  
  
 另外，必须在用于调试的本地计算机的全局程序集缓存 (GAC) 中安装程序集，该程序集包含将在远程计算机上进行调试的旧工作流的工作流定义。 例如，如果旧工作流在远程计算机 A 上运行，而您正在从本地计算机 B 对其进行调试，则计算机 B 的 GAC 中必须存在工作流定义。这样，设计器可以将正在计算机 A 上远程运行的工作流的工作标记反序列化并将其显示在计算机 B 上。有关全局程序集缓存的更多信息，请参见 MSDN Library。  
  
 [!INCLUDE[wf2](../includes/wf2-md.md)] 远程调试的作用方式与其他 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 组件的远程调试相同。 有关详细信息，请参阅[!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)]MSDN Library 中的远程调试。  
  
## <a name="see-also"></a>请参阅  
 [调试旧版工作流](../workflow-designer/debugging-legacy-workflows.md)