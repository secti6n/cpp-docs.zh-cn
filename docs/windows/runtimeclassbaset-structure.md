---
title: RuntimeClassBaseT 结构 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
dev_langs:
- C++
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ec10faf9733bbff3fb271b5465ee70a338c37898
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604988"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT 结构
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
### <a name="parameters"></a>参数  
 *RuntimeClassTypeT*  
 指定一个或多个标记的字段[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)枚举器。  
  
## <a name="remarks"></a>备注  
 提供的帮助器方法`QueryInterface`操作和入门的接口 Id。  
  
## <a name="members"></a>成员  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `RuntimeClassBaseT`  
  
## <a name="requirements"></a>要求  
 **标头：** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>请参阅  
 [参考 （Windows 运行时库）](http://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)