---
title: 编译器警告 （等级 3） C4240 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4240
dev_langs:
- C++
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f0691230454ffd935d67c99f58b857cdc1ce0f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292696"
---
# <a name="compiler-warning-level-3-c4240"></a>编译器警告（等级 3）C4240
使用的非标准扩展： 访问 classname 现在定义为访问说明符，而以前它被定义为访问说明符  
  
 在 ANSI 兼容性 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))，不能对嵌套类更改的访问权限。 在默认的 Microsoft 扩展 (/Ze) 中，可以对，并发出以下警告。  
  
## <a name="example"></a>示例  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```