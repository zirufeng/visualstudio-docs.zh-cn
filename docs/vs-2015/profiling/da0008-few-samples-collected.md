---
title: DA0008：收集的样本过少 | Microsoft Docs
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
- vs.performance.rules.DATooFewSamples
- vs.performance.8
- vs.performance.DA0008
- vs.performance.rules.DA0008
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
caps.latest.revision: 20
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 291daa031f66cc37e444a41ea085cff65a177b9d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51759381"
---
# <a name="da0008-few-samples-collected"></a>DA0008：收集的样本过少
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

规则 Id |DA0008 |  
|类别 |分析工具使用情况 |  
|分析方法 |采样 |  
|消息 |收集只是几个样本。 请考虑长的时间运行或使用更快的采样率为更有意义的结果。 |  
|规则类型 |信息 |  
  
## <a name="cause"></a>原因  
 分析运行期间仅收集了少量样本。  
  
## <a name="rule-description"></a>规则说明  
 使用采样方法时，应该收集大量具有统计学意义的样本，以确保数据反映实际的程序行为。 为了尽量减少采样错误，应尝试至少收集 1000 个程序指令执行行为的样本。 如果不收集足够的样本，则分析分析数据时可能产生误导。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 请考虑分析运行时间较长的应用程序或使用较快的采样速率，以获得具有统计学意义的结果。 有关如何更改 Visual Studio IDE 中的采样速率的信息，请参阅[如何：选择采样事件](../profiling/how-to-choose-sampling-events.md)。 有关使用分析工具命令行时如何更改采样速率的详细信息，请参阅 [VSPerfCmd](../profiling/vsperfcmd.md) 引用中的[计时器](../profiling/timer.md)。



