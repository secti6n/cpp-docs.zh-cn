---
title: __readfsbyte、 __readfsdword、 __readfsqword、 __readfsword |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readfsword
- __readfsdword
- __readfsbyte
- __readfsqword
dev_langs:
- C++
helpviewer_keywords:
- __readfsword intrinsic
- readfsword intrinsic
- __readfsdword intrinsic
- readfsbyte intrinsic
- __readfsbyte intrinsic
- readfsdword intrinsic
- readfsqword intrinsic
- __readfsqword intrinsic
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2dc016dbd2b17552d50dfdedd1208dcd3e6af22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333191"
---
# <a name="readfsbyte-readfsdword-readfsqword-readfsword"></a>__readfsbyte、__readfsdword、__readfsqword、__readfsword
**Microsoft 专用**  
  
 从指定的偏移量相对于 FS 段的开始位置读取内存。  
  
## <a name="syntax"></a>语法  
  
```  
unsigned char __readfsbyte(   
   unsigned long Offset   
);  
unsigned short __readfsword(   
   unsigned long Offset   
);  
unsigned long __readfsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readfsqword(   
   unsigned long Offset   
);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `Offset`  
 从开始处的偏移量`FS`要从其中进行读取。  
  
## <a name="return-value"></a>返回值  
 字节、 单词、 双字或四字 （如所示调用的函数的名称） 的内存内容位置`FS:[Offset]`。  
  
## <a name="requirements"></a>要求  
  
|内部函数|体系结构|  
|---------------|------------------|  
|`__readfsbyte`|x86|  
|`__readfsdword`|x86|  
|`__readfsqword`|x86|  
|`__readfsword`|x86|  
  
 **标头文件** \<intrin.h >  
  
## <a name="remarks"></a>备注  
 这些例程只能用作内部函数不可用。  
  
**结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [__writefsbyte， \__writefsdword， \__writefsqword， \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)