---
title: 事件处理全局函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85babf3155fdc94dafd5d62c2e67401e5add3663
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883994"
---
# <a name="event-handling-global-functions"></a>事件处理全局函数
此函数提供了一个事件处理程序。  
  
> [!IMPORTANT]
>  下表中列出的函数不能在 Windows 运行时中执行的应用程序中使用。  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|等待对象发出信号，同时根据需要调度窗口消息。|  

## <a name="requirements"></a>要求  
 **标头：** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop  
 等待发出对象信号，同时根据需要调度窗口消息。  
  
> [!IMPORTANT]
>  此函数不能在 Windows 运行时中执行的应用程序中使用。  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>参数  
 *n t*  
 [in]要等待的对象的句柄。  
  
### <a name="return-value"></a>返回值  
 如果该对象已发出信号，则返回 TRUE。  
  
### <a name="remarks"></a>备注  
 如果想要等待的对象事件的发生这种情况，并通知的遇到这种情况，但允许在等待过程中调度窗口消息，这非常有用。  
  
## <a name="see-also"></a>请参阅  
 [函数](../../atl/reference/atl-functions.md)
