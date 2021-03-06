---
title: 'Activationfactory:: Getiids 方法 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aaaa8d5bb0a88b9078c60fa61608e52fafd5baac
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643506"
---
# <a name="activationfactorygetiids-method"></a>ActivationFactory::GetIids 方法
检索已实现接口 ID 的数组。  
  
## <a name="syntax"></a>语法  
  
```cpp  
STDMETHOD(  
   GetIids  
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
### <a name="parameters"></a>参数  
 *iidCount*  
 此操作完成后中, 接口 Id 数*iid*数组。  
  
 *iid*  
 此操作完成后，已实现接口 ID 的数组。  
  
## <a name="return-value"></a>返回值  
 如果成功，则为 S_OK；否则为描述失败的 HRESULT。 E_OUTOFMEMORY 是可能的失败 HRESULT。  
  
## <a name="requirements"></a>要求  
 **标头：** module.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>请参阅  
 [ActivationFactory 类](../windows/activationfactory-class.md)