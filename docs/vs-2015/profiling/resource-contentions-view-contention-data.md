---
title: “资源争用”视图 - 争用数据 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.view.resourcecontention
helpviewer_keywords:
- Resource Contentions view
ms.assetid: 14a7f774-211f-4ef8-af05-94d1c8f65d2f
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b3f18cf1131e61ba88832d59e0e77f462c088bec
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482990"
---
# <a name="resource-contentions-view---contention-data"></a>“资源争用”视图 - 争用数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[资源争用视图-争用数据](https://docs.microsoft.com/visualstudio/profiling/resource-contentions-view-contention-data)。  
  
“资源争用”视图列出作为争用事件源的资源的争用数据。 如果由于另一个线程中的函数已获取对资源的独占访问权限，因此线程中的函数被迫等待获取对资源的访问权限，则会发生争用事件。 每个资源都是显示争用事件中产生的函数执行路径的调用树的根节点。  
  
## <a name="data-values"></a>数据值  
  
### <a name="resource-values"></a>资源值  
 资源行中的数据显示分析数据中被阻止访问资源的总时间，以及由于针对此资源的访问冲突而发生的争用事件总数。 资源的非独占和独占值始终是相同的。  
  
### <a name="function-values"></a>函数值  
 函数值基于在调用树中表示的执行路径中出现的函数实例。  
  
-   独占值基于函数在自己的函数体中执行语句时发生的事件。 在函数调用的函数中发生的事件不包含在独占值中。  
  
-   非独占值基于函数或函数调用的函数在执行时发生的事件。  
  
### <a name="percentage-values"></a>百分比值  
 百分比值基于分析数据中的总时间或争用事件数。 如果筛选分析运行的报告或视图，则只有经过筛选的数据中的阻塞时间和争用数才会用作总计值。  
  
## <a name="navigating-the-resource-allocation-view"></a>导航资源分配视图  
  
|列|描述|  
|------------|-----------------|  
|**名称**|资源或函数的名称。|  
|**独占阻塞的时间**|-   对于资源，是阻止访问资源并导致线程等待的总时间。<br />-   对于函数，是此函数在函数体中执行代码时阻止此函数的这些实例访问父资源的时间。 不包含此函数调用的函数中的阻塞时间。|  
|**独占阻塞的时间百分比**|-   对于资源，是此资源的阻塞时间占分析数据中的所有阻塞时间的百分比<br />-   对于函数，是这些函数实例的独占阻塞时间占分析数据中的所有阻塞时间的百分比。|  
|**独占争用**|-   对于资源，是阻止访问资源并导致线程等待的总次数。<br />-   对于函数，是此函数在函数体中执行代码时阻止此函数的这些实例访问父资源的次数。 不包含此函数调用的函数中的阻塞事件。|  
|**独占争用数百分比**|-   对于资源，是针对此资源访问权限的争用事件占分析数据中的所有争用事件的百分比。<br />-   对于函数，是这些函数实例针对父资源的独占争用事件占分析数据中的所有争用事件的百分比。|  
|**非独占阻塞的时间**|-   对于资源，是阻止访问资源并导致线程等待的总时间。<br />-   对于函数，是此函数在函数体中执行代码时阻止此函数的这些实例或这些实例调用的任何函数访问父资源的时间。|  
|**非独占阻塞的时间百分比**|-   对于资源，是此资源的阻塞时间占分析数据中的所有阻塞时间的百分比<br />-   对于函数，是这些函数实例的非独占阻塞时间占分析运行中的所有阻塞时间的百分比。|  
|**非独占争用**|-   对于资源，是阻止访问资源并导致线程等待的总次数。<br />-   对于函数，是这些函数实例针对父资源的非独占争用事件占分析运行中的所有争用事件的百分比。|  
|**非独占争用数百分比**|-   对于资源，是针对此资源访问权限的争用事件占分析运行中的所有争用事件的百分比。<br />-   对于函数，是此函数在函数体中执行代码时阻止此函数的这些实例访问父资源的次数。 不包含此函数调用的函数中的阻塞事件。|  
|**级别**|此函数在调用树中的深度。 仅在 [VSPerfReport](../profiling/vsperfreport.md) 命令行报表中。|  
|**函数行号**|此函数在源文件中的起始行号。|  
|**模块名**|函数所在模块的名称。|  
|**模块路径**|函数所在模块的路径。|  
|**进程 ID**|在其中执行模块的进程的进程 ID (PID)。|  
|**进程名**|进程的名称。|  
|**源文件**|此函数的定义所在的源文件。|


