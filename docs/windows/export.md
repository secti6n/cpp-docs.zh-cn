---
title: 导出 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.export
dev_langs:
- C++
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ad5f886c4d475cb51b370ae25549387f191ab4b6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39653126"
---
# <a name="export"></a>export
导致要放置在.idl 文件中的数据结构。  
  
## <a name="syntax"></a>语法  
  
```cpp  
[export]  
```  
  
## <a name="remarks"></a>备注  
 **导出**c + + 属性会导致置于.idl 文件中，然后，可使其可用于任何语言的二进制兼容格式的类型库中的数据结构。  
  
 无法应用**导出**属性为一个类，即使类仅具有公共成员 (等效于**结构**)。  
  
 如果要将导出未命名**enum**s 或**结构**s，它们将是开头的给定名称 **__unnamed * * * x*，其中*x*是按顺序数。  
  
 对导出有效的 typedef 的基类型、 结构、 联合、 枚举或类型标识符。  请参阅[typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287)有关详细信息。  
  
## <a name="example"></a>示例  
 下面的代码演示如何使用**导出**属性：  
  
```cpp  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## <a name="requirements"></a>要求  
  
### <a name="attribute-context"></a>特性上下文  
  
|||  
|-|-|  
|**适用对象**|**union**， **typedef**，**枚举**，**结构**，或**接口**|  
|**可重复**|否|  
|**必需的特性**|无|  
|**无效的特性**|无|  
  
 有关详细信息，请参见 [特性上下文](../windows/attribute-contexts.md)。  
  
## <a name="see-also"></a>请参阅  
 [编译器特性](../windows/compiler-attributes.md)   
 [Typedef、Enum、Union 和 Struct 特性](../windows/typedef-enum-union-and-struct-attributes.md)   