---
title: _com_error::operator = |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= _com_error objects
- = operator [C++], with specific Visual C++ objects
- operator = _com_error objects
ms.assetid: b9cc4094-d055-450c-b45a-0a95317488f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdc97982b9e8292dec1e8b5c2c49489f6803dea6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407918"
---
# <a name="comerroroperator-"></a>_com_error::operator =
**Microsoft 专用**  
  
 将现有 `_com_error` 对象赋给另一个对象。  
  
## <a name="syntax"></a>语法  
  
```  
_com_error& operator = (  
   const _com_error& that   
) throw ( );  
```  
  
#### <a name="parameters"></a>参数  
 *的*  
 一个 `_com_error` 对象。  
  
 **结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [_com_error 类](../cpp/com-error-class.md)