---
title: 选项, 文本编辑器, XML, 杂项
ms.date: 10/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Miscellaneous
ms.assetid: b6538cbe-badd-4313-a1fb-39e906736bbe
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: fed24e39b29907784d6101f7871f7a292850c457
ms.sourcegitcommit: dd839de3aa24ed7cd69f676293648c6c59c6560a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "52389346"
---
# <a name="options-text-editor-xml-miscellaneous"></a>选项, 文本编辑器, XML, 杂项

使用“杂项”属性页更改 XML 编辑器的自动完成和架构设置。 若要打开“选项”对话框，请单击“工具”菜单，然后单击“选项”。 要访问“杂项”属性页，请展开“文本编辑器” > “XML” > “杂项”节点。

## <a name="auto-insert"></a>自动插入

**结束标记**

创作 XML 元素时，文本编辑器将添加结束标记。 如果选择了元素开始标记，则编辑器会插入匹配的结束标记，包括匹配的命名空间前缀。 默认情况下选中此复选框。

**特性引号**

在创作 XML 属性时，编辑器会插入 `="` 和 `"` 字符并将插入符号 (^) 置于引号之间。 默认情况下选中此复选框。

**命名空间声明**

编辑器根据需要自动插入命名空间声明。 默认情况下选中此复选框。

**其他标记（注释、CDATA）**

自动完成注释、CDATA、DOCTYPE、处理指令和其他标记。 默认情况下选中此复选框。

## <a name="network"></a>网络

**自动下载 DTD 和架构**

架构和文档类型定义 (DTD) 自动从 HTTP 位置下载。 此功能在自动代理服务器检测启用的情况下使用 System.Net。 默认情况下选中此复选框。

## <a name="outlining"></a>大纲显示

**打开文件时进入大纲模式**

在打开文件时启用大纲功能。 默认情况下选中此复选框。

## <a name="caching"></a>缓存

**架构**

指定架构缓存的位置。 “浏览”按钮 (...) 在新窗口中打开当前架构的缓存位置。 默认位置为 \<Management Studio 安装目录>\Xml\Schemas。

## <a name="see-also"></a>请参阅

- [如何创建 XML 文档 (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation)
- [代码生成](../code-generation-in-visual-studio.md)