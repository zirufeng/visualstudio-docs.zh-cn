---
title: CA1065：不要在意外的位置引发异常
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1065
- DoNotRaiseExceptionsInUnexpectedLocations
helpviewer_keywords:
- DoNotRaiseExceptionsInUnexpectedLocations
- CA1065
ms.assetid: 4e1bade4-4ca2-4219-abc3-c7b2d741e157
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4999770367ad7b170398333cf7c7cf2cb9d1c407
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546689"
---
# <a name="ca1065-do-not-raise-exceptions-in-unexpected-locations"></a>CA1065：不要在意外的位置引发异常

|||
|-|-|
|TypeName|DoNotRaiseExceptionsInUnexpectedLocations|
|CheckId|CA1065|
|类别|Microsoft.Design|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

不应引发异常的方法引发了异常。

## <a name="rule-description"></a>规则说明

不应引发异常的方法可以进行分类，如下所示：

- 属性 Get 方法

- 事件访问器方法

- Equals 方法

- GetHashCode 方法

- ToString 方法

- 静态构造函数

- 终结器

- Dispose 方法

- 相等运算符

- 隐式强制转换运算符

以下各节讨论这些方法类型。

### <a name="property-get-methods"></a>属性 Get 方法

属性是基本上就是智能字段。 因此，它们应该表现得像尽可能多地一个字段。 字段不会引发异常，也不应该属性。 如果您有一个属性，它将引发异常，请考虑使它成为方法。

可从属性 get 方法引发以下异常：

- <xref:System.InvalidOperationException?displayProperty=fullName> 所有派生类 (包括<xref:System.ObjectDisposedException?displayProperty=fullName>)

- <xref:System.NotSupportedException?displayProperty=fullName> 所有派生类

- <xref:System.ArgumentException?displayProperty=fullName> （仅限通过索引，以获得）

- <xref:System.Collections.Generic.KeyNotFoundException> （仅限通过索引，以获得）

### <a name="event-accessor-methods"></a>事件访问器方法

事件访问器应该是简单的操作，不会引发异常。 当您尝试添加或删除事件处理程序时，事件不应引发异常。

可以从事件访问器引发以下异常：

- <xref:System.InvalidOperationException?displayProperty=fullName> 所有派生类 (包括<xref:System.ObjectDisposedException?displayProperty=fullName>)

- <xref:System.NotSupportedException?displayProperty=fullName> 所有派生类

- <xref:System.ArgumentException> 派生类

### <a name="equals-methods"></a>Equals 方法

以下**等于**方法不应引发异常：

- <xref:System.Object.Equals%2A?displayProperty=fullName>

- <xref:System.IEquatable%601.Equals%2A>

**等于**方法应返回`true`或`false`而不是引发异常。 例如，如果等于传递两个不匹配的类型则只应返回`false`而不是引发<xref:System.ArgumentException>。

### <a name="gethashcode-methods"></a>GetHashCode 方法

以下**GetHashCode**方法不应通常引发异常：

- <xref:System.Object.GetHashCode%2A>

- <xref:System.Collections.IEqualityComparer.GetHashCode%2A>

**GetHashCode**应始终返回一个值。 否则，可能会丢失哈希表中的项。

版本**GetHashCode**采用自变量可能会引发<xref:System.ArgumentException>。 但是， **Object.GetHashCode**应永远不会引发异常。

### <a name="tostring-methods"></a>ToString 方法

调试器使用<xref:System.Object.ToString%2A?displayProperty=fullName>可帮助将以字符串格式显示有关对象的信息。 因此， **ToString**不应更改对象的状态，并且它不应引发异常。

### <a name="static-constructors"></a>静态构造函数

从静态构造函数引发的异常会导致为当前应用程序域中不可用的类型。 引发静态构造函数中的异常，应具有充分的理由 （例如安全问题）。

### <a name="finalizers"></a>终结器

来自终结器引发异常会导致 CLR 快速，失败的终止进程。 因此，在终结器引发的异常应始终避免。

### <a name="dispose-methods"></a>Dispose 方法

一个<xref:System.IDisposable.Dispose%2A?displayProperty=fullName>方法不应引发异常。 中的清理逻辑的一部分通常称为 dispose`finally`子句。 因此，从 Dispose 中显式引发异常会强制用户在添加异常处理内部`finally`子句。

**Dispose （false)** 代码路径应永远不会引发异常，因为几乎总是从终结器调用 Dispose。

### <a name="equality-operators--"></a>相等运算符 (= =、 ！ =)

Equals 方法，如相等运算符应返回任一`true`或`false`，并且不应引发异常。

### <a name="implicit-cast-operators"></a>隐式强制转换运算符

因为用户通常是不知道已调用隐式强制转换运算符，隐式强制转换运算符所引发的异常是意外。 因此，应从隐式强制转换运算符不引发任何异常。

## <a name="how-to-fix-violations"></a>如何解决冲突

对于属性 getter，或者更改逻辑，以使其不再具有要引发异常，或者将属性更改为一种方法。

对于所有其他方法类型前面列出，更改逻辑，以便它不再引发异常。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

如果冲突由异常声明而不是引发的异常，则可以安全地禁止显示此规则的警告。

## <a name="related-rules"></a>相关的规则

- [CA2219：在异常子句中不引发异常](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)

## <a name="see-also"></a>请参阅

- [设计警告](../code-quality/design-warnings.md)