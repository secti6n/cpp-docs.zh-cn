---
title: _bstr_t 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7cb3d05997cfe3d803f522962ed9e7382269bd3
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404920"
---
# <a name="bstrt-class"></a>_bstr_t 类
**Microsoft 专用**  
  
 一个`_bstr_t`对象将封装[BSTR 数据类型](http://msdn.microsoft.com/1b2d7d2c-47af-4389-a6b6-b01b7e915228)。 类管理资源分配和解除分配，通过对函数调用`SysAllocString`并`SysFreeString`和其他`BSTR`Api 在适当的时候。 **_Bstr_t**类使用引用计数来避免开销过大。  
  
### <a name="construction"></a>构造  
  
|||  
|-|-|  
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|构造 `_bstr_t` 对象。|  
  
### <a name="operations"></a>操作  
  
|||  
|-|-|  
|[Assign](../cpp/bstr-t-assign.md)|将 `BSTR` 复制到 `BSTR` 包装的 `_bstr_t` 中。|  
|[附加](../cpp/bstr-t-attach.md)|将 `_bstr_t` 包装器链接到 `BSTR`。|  
|[copy](../cpp/bstr-t-copy.md)|构造封装的 `BSTR` 的副本。|  
|[分离](../cpp/bstr-t-detach.md)|返回 `BSTR` 包装的 `_bstr_t` 并从 `BSTR` 中分离 `_bstr_t`。|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|指向 `BSTR` 包装的 `_bstr_t`。|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|指向 `BSTR` 包装的 `_bstr_t` 的开头。|  
|[length](../cpp/bstr-t-length.md)|返回 `_bstr_t` 中的字符数。|  
  
### <a name="operators"></a>运算符  
  
|||  
|-|-|  
|[operator =](../cpp/bstr-t-operator-equal.md)|将新值赋给现有 `_bstr_t` 对象。|  
|[operator + =](../cpp/bstr-t-operator-add-equal-plus.md)|将字符附加到 `_bstr_t` 对象的结尾。|  
|[运算符 +](../cpp/bstr-t-operator-add-equal-plus.md)|串联两个字符串。|  
|[运算符 !](../cpp/bstr-t-operator-logical-not.md)|检查封装`BSTR`是一个 NULL 字符串。|  
|[运算符 = =、 ！ =、 \<，>， \<=、 > =](../cpp/bstr-t-relational-operators.md)|比较两个 `_bstr_t` 对象。|  
|[运算符 wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|提取指向封装的 Unicode 或多字节 `BSTR` 对象的指针。|  
  
**结束 Microsoft 专用**  
  
## <a name="requirements"></a>要求  
 **标头：** \<comutil.h >  
  
 **Lib:** comsuppw.lib 或 comsuppwd.lib (请参阅[/zc: wchar_t （wchar_t 是本机类型）](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)有关详细信息)  
  
## <a name="see-also"></a>请参阅  
 [编译器 COM 支持类](../cpp/compiler-com-support-classes.md)