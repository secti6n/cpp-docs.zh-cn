---
title: ctype_base 类 | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::ctype_base
dev_langs:
- C++
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3def685a8cd108666b3e1b8be9314fc7585a9837
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844889"
---
# <a name="ctypebase-class"></a>ctype_base 类

该类用作模板类 [ctype](../standard-library/ctype-class.md) 的 facet 基类。 一种 ctype 类的基类，用于定义枚举类型来分类或测试单个字符或整个范围内的字符。

## <a name="syntax"></a>语法

```cpp
struct ctype_base : public locale::facet
{
    enum
    {
        alnum,
        alpha,
        cntrl,
        digit,
        graph,
        lower,
        print,
        punct,
        space,
        upper,
        xdigit
    };
    typedef short mask;

    ctype_base( size_t _Refs = 0 );
    ~ctype_base();
};
```

## <a name="remarks"></a>备注

它定义了枚举掩码。 每个枚举常量都表现为一种不同方式来对字符进行分类，正如在标头 \<ctype.h 1> 中声明的具有类似名称的函数所定义。 这些常量包括：

- **space**（函数 [isspace](../standard-library/locale-functions.md#isspace)）

- **print**（函数 [isprint](../standard-library/locale-functions.md#isprint)）

- **cntrl**（函数 [iscntrl](../standard-library/locale-functions.md#iscntrl)）

- **upper**（函数 [isupper](../standard-library/locale-functions.md#isupper)）

- **lower**（函数 [islower](../standard-library/locale-functions.md#islower)）

- **digit**（函数 [isdigit](../standard-library/locale-functions.md#isdigit)）

- **punct**（函数 [ispunct](../standard-library/locale-functions.md#ispunct)）

- **xdigit**（函数 [isxdigit](../standard-library/locale-functions.md#isxdigit)）

- **alpha**（函数 [isalpha](../standard-library/locale-functions.md#isalpha)）

- **alnum**（函数 [isalnum](../standard-library/locale-functions.md#isalnum)）

- **graph**（函数 [isgraph](../standard-library/locale-functions.md#isgraph)）

通过实现或运算这些常量，可以确定分类组合的特征。 具体而言，它是始终为 true， **alnum** = = (**字母** &#124; **数字**\)和**graph** \=\= \( **alnum** &#124; **标点符号**)。

## <a name="requirements"></a>要求

**标头：** \<locale>

**命名空间：** std

## <a name="see-also"></a>请参阅

[C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
