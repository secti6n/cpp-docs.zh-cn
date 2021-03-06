---
title: __sidt |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __sidt
dev_langs:
- C++
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29e41b0edd9b2a3da1046888f16a55e19f2d9f20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324507"
---
# <a name="sidt"></a>__sidt
**Microsoft 专用**  
  
 将中断描述符表寄存器 (IDTR) 的值存储在指定的内存位置。  
  
## <a name="syntax"></a>语法  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|[in] `Destination`|指向存储 IDTR 的内存位置的指针。|  
  
## <a name="requirements"></a>要求  
  
|内部函数|体系结构|  
|---------------|------------------|  
|`__sidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **标头文件** \<intrin.h >  
  
## <a name="remarks"></a>备注  
 `__sidt`函数等同于`SIDT`计算机指令。 有关详细信息，搜索文档中，"Intel 体系结构软件开发人员手册，卷 2： 指令集引用，"在[Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)站点。  
  
**结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)