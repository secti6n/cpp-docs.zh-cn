---
title: 服务器注册全局函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
dev_langs:
- C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8bed065eb959d959086133a757b7ca3594214719
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883275"
---
# <a name="server-registration-global-functions"></a>服务器注册全局函数
这些函数提供支持注册和注销对象映射中的服务器对象。  
  
> [!IMPORTANT]
>  下表中列出的函数不能在 Windows 运行时中执行的应用程序中使用。  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|调用此函数可在对象映射中注册所有对象。|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|调用此函数可在对象映射中注销所有对象。|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|调用此函数可注册类对象。|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|若要吊销从 COM 模块类对象，调用此函数。|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|此函数调用以获取类对象。|  

## <a name="requirements"></a>要求  
 **标头：** atlbase.h  
   
##  <a name="atlcommoduleregisterserver"></a>  AtlComModuleRegisterServer  
 调用此函数可在对象映射中注册所有对象。  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>参数  
 *pComModule*  
 对 COM 模块的指针。  
  
 *bRegTypeLib*  
 如果类型库的注册，则为 TRUE。  
  
 *pCLSID*  
 指向要注册的对象的 CLSID。 如果为 NULL，将注册对象映射中的所有对象。  
  
### <a name="return-value"></a>返回值  
 返回成功，则为 S_OK 或失败时的错误 HRESULT。  
  
### <a name="remarks"></a>备注  
 `AtlComModuleRegisterServer` 指导 ATL 自动生成对象映射并在映射中注册的每个对象。 如果*pCLSID*为 NULL，则仅通过引用的对象不是*pCLSID*注册; 否则注册的所有对象。  
  
 调用此函数[CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver)。  
  
##  <a name="atlcommoduleunregisterserver"></a>  AtlComModuleUnregisterServer  
 调用此函数可在对象映射中注销所有对象。  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>参数  
 *pComModule*  
 对 COM 模块的指针。  
  
 *bUnRegTypeLib*  
 如果类型库的注册，则为 TRUE。  
  
 *pCLSID*  
 指向要注销的对象的 CLSID。 如果为 NULL 对象映射中的所有对象都将注销。  
  
### <a name="return-value"></a>返回值  
 返回成功，则为 S_OK 或失败时的错误 HRESULT。  
  
### <a name="remarks"></a>备注  
 `AtlComModuleUnregisterServer` 演示了 ATL 对象映射并注销映射中的每个对象。 如果*pCLSID*为 NULL，则仅通过引用的对象不是*pCLSID*注销; 否则为的所有对象会撤消注册。  
  
 调用此函数[CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver)。  
  
##  <a name="atlcommoduleregisterclassobjects"></a>  AtlComModuleRegisterClassObjects  
 调用此函数可注册类对象。  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>参数  
 *pComModule*  
 对 COM 模块的指针。  
  
 *dwClsContext*  
 指定在其中运行的类对象的上下文。 可能的值为 CLSCTX_INPROC_SERVER、 CLSCTX_INPROC_HANDLER 或 CLSCTX_LOCAL_SERVER。 请参阅[CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716)的更多详细信息。  
  
 *dwFlags*  
 确定指向类对象的连接类型。 可能的值为 REGCLS_SINGLEUSE、 REGCLS_MULTIPLEUSE 或 REGCLS_MULTI_SEPARATE。 请参阅[结合](http://msdn.microsoft.com/library/windows/desktop/ms679697)的更多详细信息。  
  
### <a name="return-value"></a>返回值  
 返回成功，则为 S_OK 或失败时的错误 HRESULT。  
  
### <a name="remarks"></a>备注  
 使用此帮助器函数[CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) （ATL 7.0 中已过时） 和[CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects)。  
  
##  <a name="atlcommodulerevokeclassobjects"></a>  AtlComModuleRevokeClassObjects  
 调用此函数可从运行对象表中移除类工厂。  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>参数  
 *pComModule*  
 对 COM 模块的指针。  
  
### <a name="return-value"></a>返回值  
 返回成功，则为 S_OK 或失败时的错误 HRESULT。  
  
### <a name="remarks"></a>备注  
 使用此帮助器函数[CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) （ATL 7.0 中已过时） 和[CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects)。  
  
##  <a name="atlcommodulegetclassobject"></a>  AtlComModuleGetClassObject  
 调用此函数可返回类工厂。  
  
```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```  
  
### <a name="parameters"></a>参数  
 *pComModule*  
 对 COM 模块的指针。  
  
 *rclsid*  
 若要创建的对象的 CLSID。  
  
 *riid*  
 所请求的接口的 IID。  
  
 *ppv*  
 通过标识的接口指针的指针*riid*。 如果该对象不支持此接口， *ppv*设置为 NULL。  
  
### <a name="return-value"></a>返回值  
 返回成功，则为 S_OK 或失败时的错误 HRESULT。  
  
### <a name="remarks"></a>备注  
 使用此帮助器函数[CComModule::GetClassObject](ccommodule-class.md#getclassobject) （ATL 7.0 中已过时） 和[CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject)。  
  
## <a name="see-also"></a>请参阅  
 [函数](../../atl/reference/atl-functions.md)
