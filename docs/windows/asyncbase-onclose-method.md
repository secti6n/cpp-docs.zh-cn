---
title: 'Asyncbase:: Onclose 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnClose
dev_langs:
- C++
helpviewer_keywords:
- OnClose method
ms.assetid: 96766450-c262-4611-8534-7d190b799142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c1b888b9d3e3f3c80c3aff40f5fd545ece9cca6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650633"
---
# <a name="asyncbaseonclose-method"></a>AsyncBase::OnClose 方法
当在派生类中重写，会关闭一个异步操作。  
  
## <a name="syntax"></a>语法  
  
```cpp  
virtual void OnClose(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>要求  
 **标头：** async.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>请参阅  
 [AsyncBase 类](../windows/asyncbase-class.md)   
 [AsyncBase::Close 方法](../windows/asyncbase-close-method.md)