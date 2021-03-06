---
title: 工作流设计器-CorrelationScope 活动设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.CorrelationScope.UI
ms.assetid: 75f20664-9042-464d-8e2b-148d365a2286
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d1da881dfb7f7a8c063b94e49198d1b299b2e47b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942044"
---
# <a name="correlationscope-activity-designer"></a>CorrelationScope 活动设计器

**CorrelationScope**活动设计器用于创建和配置<xref:System.ServiceModel.Activities.CorrelationScope>提供子消息传递活动使用的隐式管理的活动<xref:System.ServiceModel.Activities.CorrelationHandle>对象。

## <a name="the-correlationscope-activity"></a>CorrelationScope 活动

<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> 属性指定用于管理子消息传递活动的 <xref:System.ServiceModel.Activities.CorrelationHandle>。 将 <xref:System.ServiceModel.Activities.Send> 中包含的 <xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.CorrelationScope.Body%2A> 活动配置为使用包含 <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> 活动的 <xref:System.ServiceModel.Activities.CorrelationScope> 属性以执行相关。

### <a name="use-the-correlationscope-activity-designer"></a>使用 CorrelationScope 活动设计器

**CorrelationScope**活动设计器可在**消息传送**类别**工具箱**，这通过单击来访问**工具箱**左侧和右侧的工作流设计器上的选项卡。 或者，选择**工具箱**从**视图**菜单中或按**Ctrl**+**Alt** + **X**。

**CorrelationScope**活动设计器可以从拖动**工具箱**和放置到工作流设计器图面。 这将创建<xref:System.ServiceModel.Activities.CorrelationScope>默认值的活动**DisplayName** CorrelationScope。 <xref:System.Activities.Activity.DisplayName%2A>可以在的标头中编辑**CorrelationScope**活动设计器中或在**DisplayName**框**属性**窗口。

若要指定<xref:System.ServiceModel.Activities.CorrelationHandle>子消息传递活动使用，请选择旁的省略号按钮**CorrelatesWith**字段中**属性**窗口中显示**表达式编辑器**对话框。 还可以在活动设计器图面上设置此属性。

范围在相关之内的活动所指定的设计器中的放置**正文**框中**CorrelationScope**设计器。

### <a name="the-correlationscope-properties"></a>CorrelationScope 属性

下表列出 <xref:System.ServiceModel.Activities.CorrelationScope> 属性并说明如何在设计器中使用它们。 这些属性可以是中编辑**属性**窗口或在工作流设计器图面，并经常在这种。

|属性名|必需|用法|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.InitializeCorrelation> 活动的可选友好名称。|
|<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A>|False|指定用于管理子消息传递活动的 <xref:System.ServiceModel.Activities.CorrelationHandle>。 如果未设置此属性，则 <xref:System.ServiceModel.Activities.CorrelationScope> 会自动创建一个隐式 <xref:System.ServiceModel.Activities.CorrelationHandle>。|
|<xref:System.ServiceModel.Activities.CorrelationScope.Body%2A>|False|指定处于相关范围之内的活动。|

## <a name="see-also"></a>请参阅

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Receive](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Send](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)