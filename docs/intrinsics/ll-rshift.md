---
title: __ll_rshift |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
dev_langs:
- C++
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e086339c41f789323cb4aab386a96dae27a0eeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324923"
---
# <a name="llrshift"></a>__ll_rshift
**Microsoft 专用**  
  
 第二个参数所指定的位数右移右侧的第一个参数指定的 64 位值。  
  
## <a name="syntax"></a>语法  
  
```  
__int64 __ll_rshift(  
   __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>参数  
 [in] `Mask`  
 要移动到了右边的 64 位整数值。  
  
 [in] `nBit`  
 要移位，模 64，在 x64 上和取模 x86 上的 32 位的数。  
  
## <a name="return-value"></a>返回值  
 掩码移动`nBit`bits。  
  
## <a name="requirements"></a>要求  
  
|内部函数|体系结构|  
|---------------|------------------|  
|`__ll_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **标头文件** \<intrin.h >  
  
## <a name="remarks"></a>备注  
 如果第二个参数大于 64 x64 (32 x86 上) 上，该数字执行模 64 (在 x86 32) 来确定要位移的位数数。 `ll`前缀指示这是一个操作上`long long`、 另一名称`__int64`，64 位有符号的整型。  
  
## <a name="example"></a>示例  
  
```  
// ll_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_rshift)  
  
int main()  
{  
   __int64 Mask = - 0x100;  
   int nBit = 4;  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
   Mask = __ll_rshift(Mask, nBit);  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
}  
```  
  
## <a name="output"></a>输出  
  
```  
ffffffffffffff00  
 - 100  
fffffffffffffff0  
 - 10  
```  
  
 **请注意**如果`_ull_rshift`已被使用，向右移动值 MSB 已经是零，因此所需的结果将不具有已获取对于负值。  
  
**结束 Microsoft 专用**  
  
## <a name="see-also"></a>请参阅  
 [编译器内部函数](../intrinsics/compiler-intrinsics.md)   
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)