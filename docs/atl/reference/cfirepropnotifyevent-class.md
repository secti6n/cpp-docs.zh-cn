---
title: CFirePropNotifyEvent 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
dev_langs:
- C++
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20fd9c660f036c04ea2ca7d06d04315391504e3e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881524"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent 类
此类提供用于通知与控件属性更改有关容器的接收器的方法。  
  
> [!IMPORTANT]
>  不能在 Windows 运行时中执行的应用程序中使用此类和其成员。  
  
## <a name="syntax"></a>语法  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>成员  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|（静态）通知控件属性已更改的容器的接收器。|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|（静态）通知即将更改控件属性的容器的接收器。|  
  
## <a name="remarks"></a>备注  
 `CFirePropNotifyEvent` 有两个方法，以通知控件属性已更改或将要更改的容器的接收器。  
  
 如果实现您的控件的类派生自`IPropertyNotifySink`，则`CFirePropNotifyEvent`调用时调用方法`FireOnRequestEdit`或`FireOnChanged`。 如果你的控件类不派生自`IPropertyNotifySink`，对这些函数的调用返回 S_OK。  
  
 有关创建控件的详细信息，请参阅[ATL 教程](../../atl/active-template-library-atl-tutorial.md)。  
  
## <a name="requirements"></a>要求  
 **标头：** atlctl.h  
  
##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged  
 通知所有连接[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) （上对象的每个连接点） 指定的对象属性已更改的接口。  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>参数  
 *pUnk*  
 [in]指向`IUnknown`将通知发送到的对象。  
  
 *dispID*  
 [in]已更改的属性的标识符。  
  
### <a name="return-value"></a>返回值  
 一个标准的 HRESULT 值。  
  
### <a name="remarks"></a>备注  
 此函数是安全地调用即使您的控件不支持连接点。  
  
##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit  
 通知所有连接[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)即将更改指定的对象属性 （在上对象的每个连接点） 的接口。  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>参数  
 *pUnk*  
 [in]指向`IUnknown`将通知发送到的对象。  
  
 *dispID*  
 [in]要更改的属性的标识符。  
  
### <a name="return-value"></a>返回值  
 一个标准的 HRESULT 值。  
  
### <a name="remarks"></a>备注  
 此函数是安全地调用即使您的控件不支持连接点。  
  
## <a name="see-also"></a>请参阅  
 [类概述](../../atl/atl-class-overview.md)
