---
title: 链接器工具错误 LNK2023 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2023
dev_langs:
- C++
helpviewer_keywords:
- LNK2023
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b53fba3743d6d072930e430c15b79e0e31d68d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302602"
---
# <a name="linker-tools-error-lnk2023"></a>链接器工具错误 LNK2023
错误的 dll 或入口点\<dll 或入口点 >  
  
 链接器正在加载 msobj90.dll 不正确的版本。 确保 link.exe 和 msobj90.dll 在你的路径具有相同的版本。  
  
 Msobj90.dll 的依赖项可能不存在。 Msobj90.dll 的依赖项列表是：  
  
-   Msvcr90.dll  
  
-   Kernel32.dll  
  
 检查你的计算机可能已过期的 msobj90.dll 的任何其他副本进行。