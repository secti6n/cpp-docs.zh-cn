---
title: 在 __asm 块中使用 C 或 c + + |Microsoft 文档
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline assembly, mixing instructions with C/C++ statements
- symbols, in __asm blocks
- macros, __asm blocks
- preprocessor directives, used in __asm blocks
- type names, used in __asm blocks
- preprocessor directives
- preprocessor, directives
- constants, in __asm blocks
- comments, in __asm blocks
- typedef names, used in __asm blocks
- __asm keyword [C++], C/C++ elements in
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96ed46cdf44ccacee806dd03bf7eacca26eec32d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120934"
---
# <a name="using-c-or-c-in-asm-blocks"></a>在 __asm 块中使用 C 或 C++

* * Microsoft 专用 * *

由于内联程序集指令可以与 C 或 C++ 语句组合，因此可以通过名称引用 C 或 C++ 变量，或者使用这些语言的多个其他元素。

`__asm` 块可以使用下列语言元素：

- 符号（包括标签、变量和函数名称）

- 常量（包括符号常量和 `enum` 成员）

- 宏和预处理器指令

- 注释 (同时__/ \* \* /__ 和__//__ )

- 类型名称（其中的 MASM 类型是合法的）

- `typedef` 如运算符通常使用的名称**PTR**和**类型**或指定结构或联合成员

在 `__asm` 块内，您可以使用 C 表示法或汇编基数表示法指定整数常量（例如，0x100 和 100h 等效）。 这允许您在 C 中定义（使用 `#define`）常量，然后在 C 或 C++ 以及程序的程序集部分中使用该常量。 您还可以通过在其前面放置 0 以八进制指定常量。 例如，0777 指定一个八进制常量。

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

- [在 __asm 块中使用运算符](../../assembler/inline/using-operators-in-asm-blocks.md)

- [使用 C 或 c + + 中 __asm 块](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [在 __asm 块中访问 C 或 C++ 数据](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [使用内联程序集编写函数](../../assembler/inline/writing-functions-with-inline-assembly.md)

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[内联汇编程序](../../assembler/inline/inline-assembler.md)
