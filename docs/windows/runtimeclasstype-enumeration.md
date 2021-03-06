---
title: RuntimeClassType 枚举 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4464d236a85e06bf907f738657a4a0707e14a5e1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603496"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType 枚举
指定的类型[RuntimeClass](../windows/runtimeclass-class.md)支持实例。  
  
## <a name="syntax"></a>语法  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>成员  
  
### <a name="values"></a>值  
  
|名称|描述|  
|----------|-----------------|  
|`ClassicCom`|经典的 COM 运行时类。|  
|`Delegate`|等效于 `ClassicCom`。|  
|`InhibitFtmBase`|禁用`FtmBase`支持的同时，`__WRL_CONFIGURATION_LEGACY__`未定义。|  
|`InhibitWeakReference`|禁用弱引用支持。|  
|`WinRt`|Windows 运行时类。|  
|`WinRtClassicComMix`|`WinRt` 和 `ClassicCom` 的组合。|  
  
## <a name="requirements"></a>要求  
 **标头：** implements.h  
  
 **命名空间：** Microsoft::WRL  
  
## <a name="see-also"></a>请参阅  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)