---
title: 编译器警告 （等级 1） C4228 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4228
dev_langs:
- C++
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 023bf60930a53b6bd881680caebb78c151406df4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276785"
---
# <a name="compiler-warning-level-1-c4228"></a>编译器警告（等级 1）C4228
使用的非标准扩展： 限定符在声明符列表中的逗号之后将被忽略  
  
 利用限定符喜欢**const**或`volatile`逗号声明变量时是 Microsoft 扩展后 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。  
  
## <a name="example"></a>示例  
  
```  
// C4228.cpp  
// compile with: /W1  
int j, const i = 0;  // C4228  
int k;  
int const m = 0;  // ok  
int main()  
{  
}  
```