---
title: 如何： 更改 DataContext 方法 （O-R 设计器） 的返回类型 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5b66bff-6dbb-43c0-bffa-317133ca5b9e
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4999c9fd273b78ff740e53c25bbe5a4b0a3017f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49211739"
---
# <a name="how-to-change-the-return-type-of-a-datacontext-method-or-designer"></a>如何： 更改 DataContext 方法 （O/R 设计器） 的返回类型
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
根据在 <xref:System.Data.Linq.DataContext>中放置存储过程或函数的位置不同，[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] 方法（基于该存储过程或函数创建）的返回类型也有所不同。 如果直接将项放在现有实体类上，则将创建具有该实体类返回类型的 <xref:System.Data.Linq.DataContext> 方法（如果该存储过程或函数返回的数据架构与实体类的形状相匹配）。 如果将项放在 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]的空白区域，则将创建返回自动生成类型的 <xref:System.Data.Linq.DataContext> 方法。 在将 <xref:System.Data.Linq.DataContext> 方法添加到方法窗格后可以更改该方法的返回类型。 若要检查或更改的返回类型<xref:System.Data.Linq.DataContext>方法中，选择它，然后单击**返回类型**中的属性**属性**窗口。  
  
> [!NOTE]
>  无法还原<xref:System.Data.Linq.DataContext>方法具有返回类型设置为实体类，以使用返回自动生成的类型**属性**窗口。 若要将 <xref:System.Data.Linq.DataContext> 方法恢复为返回自动生成类型，您必须将原始数据库对象再次拖动到 O/R 设计器上。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-change-the-return-type-of-a-datacontext-method-from-the-auto-generated-type-to-an-entity-class"></a>将 DataContext 方法的返回类型从自动生成类型更改为实体类  
  
1.  在方法窗格中选择该 <xref:System.Data.Linq.DataContext> 方法。  
  
2.  选择**返回类型**中**属性**窗口，然后选择一个可用的实体类中**返回类型**列表。 如果列表中没有您需要的实体类，可将该实体类添加到列表中，或在 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]中创建该实体类并将其添加到列表中。  
  
3.  保存 .dbml 文件。  
  
### <a name="to-change-the-return-type-of-a-datacontext-method-from-an-entity-class-back-to-the-auto-generated-type"></a>将 DataContext 方法的返回类型从实体类重新更改为自动生成类型  
  
1.  在方法窗格中选择该 <xref:System.Data.Linq.DataContext> 方法并删除该方法。  
  
2.  将数据库对象从**服务器资源管理器**/**数据库资源管理器**O/R 设计器的空白区域。  
  
3.  保存 .dbml 文件。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [DataContext 方法 （O/R 设计器）](../data-tools/datacontext-methods-o-r-designer.md)   
 [如何：创建映射到存储过程和函数的 DataContext 方法（O/R 设计器）](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)

