---
title: setvbuf 常量 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs:
- C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d4292ae29602b5890a167a3e2c29e460d65373f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407959"
---
# <a name="setvbuf-constants"></a>setvbuf 常量
## <a name="syntax"></a>语法  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>备注  
 这些常量表示 `setvbuf` 的缓冲区类型。  
  
 可能的值由下列清单常量提供：  
  
|返回的常量|含义|  
|--------------|-------------|  
|`_IOFBF`|完全缓冲：将使用调用 `setvbuf` 时指定的缓冲区，其大小如 `setvbuf` 调用中所指定。 如果缓冲区指针为 NULL，则将使用自动分配的指定大小的缓冲区。|  
|`_IOLBF`|与 `_IOFBF` 相同。|  
|`_IONBF`|将不会使用缓冲区，无论调用 `setvbuf` 的参数如何。|  
  
## <a name="see-also"></a>请参阅  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [全局常量](../c-runtime-library/global-constants.md)