---
title: DA0503：所分析的进程的平均工作集（以字节为单位）| Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.503
- vs.performance.DA0503
- vs.performance.rules.DA0503
ms.assetid: 9047a494-eaaf-4679-b422-c64e8bde77a4
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f13dc584c8865fa2caa502db0708a27c5d1a8f3
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51816926"
---
# <a name="da0503-average-working-set-in-bytes-for-the-process-being-profiled"></a>DA0503：所分析的进程的平均工作集(以字节为单位)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

规则 Id |DA0503 |  
|类别 |资源监视 |  
|分析方法 |所有 |  
|消息 |此信息仅作为信息收集。 进程工作集计数器测量由正在分析的进程使用的物理内存的使用情况。 报告的值计算出所有测量时间间隔的平均值。 |  
|规则类型 |信息 |  
  
 使用采样法、.NET 内存或资源争用方法进行分析时，必须收集至少 10 个样本才能触发此规则。  
  
## <a name="rule-description"></a>规则说明  
 此消息用于报告此进程当前使用的平均物理内存字节数（工作集）。 进程工作集表示当前位于物理内存中的进程地址空间中的页面。  
  
 报告的值包括进程已引用的共享内存段中的驻留页面。 进程引用的共享 DLL 包含在计算的共享内存段中。 受共享内存段的影响，进程工作集的值可能高于进程已经分配的虚拟内存量。  
  
 报告的值是所分析的进程处于活动状态的所有测量时间间隔的平均值。  
  
 进程工作集的大小反映进程当前使用的虚拟内存量。 它还受可用于运行应用程序的物理内存量（或 RAM）和其他运行的进程对该物理内存的争用量的影响。 如果物理内存受到约束，则进程工作集往往存在较大差别，因为操作系统将尝试从进程工作集通过定期修整活动程度相当低的进程，以平衡整个活动进程中的内存使用情况。  
  
 有关进程工作集的详细信息，请参阅 MSDN 上 Windows 内存管理文档中的 [Working Set](http://go.microsoft.com/fwlink/?LinkId=177830)（工作集）。  
  
## <a name="how-to-use-rule-data"></a>如何使用规则数据  
 若要了解不同分析方案中应用程序的性能，可使用规则值比较不同版本程序的性能。  
  
 双击“错误列表”窗口中的消息，导航到分析数据的[标记视图](../profiling/marks-view.md)。 查找 **Process\Working Set** 和 **Memory\Pages/sec** 列。 比较两个列，并确定是否存在与增加的页面 IO 活动关联的特定阶段的程序执行。



