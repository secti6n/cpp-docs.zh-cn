---
title: 'Comptr:: Operator-&gt;运算符 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator->
dev_langs:
- C++
helpviewer_keywords:
- operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1530f7998f2597aeb2fe46dba09f4844b471cd93
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644825"
---
# <a name="comptroperator-gt-operator"></a>Comptr:: Operator-&gt;运算符
检索指向当前模板参数所指定类型的指针。  
  
## <a name="syntax"></a>语法  
  
```cpp  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>返回值  
 指向当前模板类型名称由指定的类型。  
  
## <a name="remarks"></a>备注  
 此帮助器函数删除由使用 STDMETHOD 宏导致不必要的开销。 此功能，可以`IUnknown`类型**专用**而不是**虚拟**。  
  
## <a name="requirements"></a>要求  
 **标头：** client.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>请参阅  
 [ComPtr 类](../windows/comptr-class.md)