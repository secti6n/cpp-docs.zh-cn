---
title: 'Asyncbase:: Getonprogress 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::GetOnProgress
dev_langs:
- C++
helpviewer_keywords:
- GetOnProgress method
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9446c94039db0ff81826e77d71a2a9539be4b276
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643142"
---
# <a name="asyncbasegetonprogress-method"></a>AsyncBase::GetOnProgress 方法
将当前进度事件处理程序的地址复制到指定的变量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
STDMETHOD(  
   GetOnProgress  
)(TProgress** progressHandler);  
```  
  
### <a name="parameters"></a>参数  
 *progressHandler*  
 存储当前进度事件处理程序的地址的位置。  
  
## <a name="return-value"></a>返回值  
 如果成功，则为 S_OK否则为 E_ILLEGAL_METHOD_CALL。  
  
## <a name="requirements"></a>要求  
 **标头：** async.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>请参阅  
 [AsyncBase 类](../windows/asyncbase-class.md)