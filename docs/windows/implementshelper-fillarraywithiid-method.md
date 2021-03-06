---
title: 'Implementshelper:: Fillarraywithiid 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f60035ee-b7d6-4a08-966d-f88c646944c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da38eddae5ab9c49da98a4c5e9f383d59d110ee1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608317"
---
# <a name="implementshelperfillarraywithiid-method"></a>ImplementsHelper::FillArrayWithIid 方法
支持 WRL 基础结构，不应在代码中直接使用。  
  
## <a name="syntax"></a>语法  
  
```  
void FillArrayWithIid(  
   _Inout_ unsigned long *index,   
   _Inout_ IID* iids) throw();  
```  
  
#### <a name="parameters"></a>参数  
 *index*  
 一个从零开始的索引，该值指示此操作的起始数组元素。 此操作完成后，*索引*都会增加 1。  
  
 *iid*  
 类型 Iid 的数组。  
  
## <a name="remarks"></a>备注  
 将插入到指定的数组元素指定由当前第零个模板参数的接口 ID。  
  
## <a name="requirements"></a>要求  
 **标头：** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>请参阅  
 [ImplementsHelper 结构](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details 命名空间](../windows/microsoft-wrl-details-namespace.md)