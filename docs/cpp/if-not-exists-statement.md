---
title: __if_not_exists 语句 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bee63ace276863a30c4ec81d970ba3bf5fd29e40
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405280"
---
# <a name="ifnotexists-statement"></a>__if_not_exists 语句
**__If_not_exists**语句测试是否存在指定的标识符。 如果该标识符不存在，则执行指定的语句块。  
  
## <a name="syntax"></a>语法  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|*identifier*|要测试其存在性的标识符。|  
|*语句*|一个或多个时要执行的语句*标识符*不存在。|  
  
## <a name="remarks"></a>备注  
  
> [!CAUTION]
>  若要实现最可靠的结果，请使用 **__if_not_exists**以下约束条件下的语句。  
  
-   将应用 **__if_not_exists**语句仅简单类型，而不是模板。  
  
-   将应用 **__if_not_exists**到的内部或外部类标识符的语句。 不适用于 **__if_not_exists**到本地变量的语句。  
  
-   使用 **__if_not_exists**仅在函数体中的语句。 在函数体外部区域 **__if_not_exists**语句可以测试仅完全定义的类型。  
  
-   在测试重载函数时，不能测试特定形式的重载。  
  
 对补充 **__if_not_exists**语句是[__if_exists](../cpp/if-exists-statement.md)语句。  
  
## <a name="example"></a>示例  
 有关如何使用的示例 **__if_not_exists**，请参阅[__if_exists 语句](../cpp/if-exists-statement.md)。  
  
## <a name="see-also"></a>请参阅  
 [选择语句](../cpp/selection-statements-cpp.md)   
 [关键字](../cpp/keywords-cpp.md)   
 [__if_exists 语句](../cpp/if-exists-statement.md)