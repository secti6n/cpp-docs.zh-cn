---
title: 编译器警告 （等级 1） C4138 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4138
dev_langs:
- C++
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0865935c30c4934684c7a12e50ab26f3e8b12c4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277028"
---
# <a name="compiler-warning-level-1-c4138"></a>编译器警告（等级 1）C4138
在注释外找到“*/”  
  
 结束注释分隔符前面没有开始注释分隔符。 编译器将假定星号 (**\***) 和正斜杠 (/) 之间留有一个空格。  
  
## <a name="example"></a>示例  
  
```  
// C4138a.cpp  
// compile with: /W1  
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning  
int main()  
{  
}  
```  
  
 此警告可由嵌套注释引起。  
  
 如果注释掉包含注释的代码段，在 **#if / #endif** 块中包含代码，并将控制表达式设置为零，可能会解决此警告：  
  
```  
// C4138b.cpp  
// compile with: /W1  
#if 0  
int my_variable;   /* Declaration currently not needed */  
#endif  
int main()  
{  
}  
```