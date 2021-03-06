---
title: 注册表和类型库全局函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetPerUserRegistration
- afxpriv/ATL::AfxRegCreateKey
- afxpriv/ATL::AfxRegDeleteKey
- atlbase/ATL::AtlRegisterTypeLib
- afxpriv/ATL::AfxRegOpenKey
- afxpriv/ATL::AfxRegOpenKeyEx
- afxdisp/ATL::AfxUnregisterPreviewHandler
- atlbase/ATL::AtlSetPerUserRegistration
- atlbase/ATL::AtlUnRegisterTypeLib
- atlbase/ATL::AtlLoadTypeLib
- atlbase/ATL::AtlUpdateRegistryFromResourceD
- atlbase/ATL::RegistryDataExchange
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84328c35ceb9a4cf2631f27e9f860a1f60e33c55
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885410"
---
# <a name="registry-and-typelib-global-functions"></a>注册表和类型库全局函数
这些函数提供用于加载和注册类型库的支持。  
  
> [!IMPORTANT]
>  下表中列出的函数不能在 Windows 运行时中执行的应用程序中使用。  
  
|||  
|-|-|  
|[AfxRegCreateKey](#afxrefcreatekey)|创建指定的注册表项。|
|[AfxRegDeleteKey](#afxrefdeletekey)|删除指定的注册表项。|
|[AfxRegisterPreviewHandler](#afxregisterpreviewhandler)|用于注册预览处理程序的帮助程序。|
|[AfxUnregisterPreviewHandler](#afxunregisterpreviewhandler)| 用于注销预览处理程序的帮助程序。 |
|[AtlRegisterTypeLib](#atlregistertypelib)|调用此函数可注册类型库。|  
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|此函数调用以注销类型库|  
|[AfxRegOpenKey](#afxregopenkey)|打开指定的注册表项。|
|[AfxRegOpenKeyEx](#afxregopenkeyex)|打开指定的注册表项。|
|[AtlLoadTypeLib](#atlloadtypelib)|调用此函数可加载类型库。|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|调用此函数可从提供的资源中更新注册表。|  
|[RegistryDataExchange](#registrydataexchange)|调用此函数可在系统注册表中进行读取或写入。 调用[注册表数据交换宏](../../atl/reference/registry-data-exchange-macros.md)。|  
  
 这些函数来控制该程序使用来将信息存储在注册表中的哪个节点。  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|检索应用程序将注册表访问重定向是否**HKEY_CURRENT_USER** ( **HKCU**) 节点。|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|设置是否在应用程序将注册表访问重定向**HKEY_CURRENT_USER** ( **HKCU**) 节点。|  

### <a name="requirements"></a>要求  
 **标头：** atlbase.h

## <a name="atlgetperuserregistration"></a> AtlGetPerUserRegistration
使用此函数可确定应用程序是否将注册表访问重定向**HKEY_CURRENT_USER** (**HKCU**) 节点。  
  
### <a name="syntax"></a>语法  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>参数  
 [out]*pEnabled*  
 TRUE 表示注册表信息将定向到**HKCU**节点;FALSE 表示应用程序将注册表信息写入到默认的节点。 默认的节点是**HKEY_CLASSES_ROOT** (**HKCR**)。  
  
### <a name="return-value"></a>返回值  
 如果该方法成功，则为 S_OK，否则 HRESULT 错误代码如果出现错误。  
  
### <a name="remarks"></a>备注  
 默认情况下不启用注册表重定向。 如果启用此选项时，注册表访问重定向到**HKEY_CURRENT_USER\Software\Classes**。  
  
 重定向不是全局的。 仅 MFC 和 ATL 框架受此注册表重定向。  
  
### <a name="requirements"></a>要求  
 **标头：** atlbase.h  

 ## <a name="afxregcreatekey"></a> AfxRegCreateKey
 创建指定的注册表项。  
  
### <a name="syntax"></a>语法  
  
```  
LONG AFXAPI AfxRegCreateKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>参数  
 *hKey*  
 打开注册表项句柄。  
  
 *lpSubKey*  
 此函数将打开或创建的密钥的名称。  
  
 *phkResult*  
 指向一个变量来接收打开或创建密钥的句柄的指针。  
  
 *pTM*  
 指向 `CAtlTransactionManager` 对象的指针。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值为 ERROR_SUCCESS。 如果函数失败，返回值是在 Winerror.h 中定义一个非零错误代码。  

### <a name="requirements"></a>要求  
 **标头：** afxpriv.h  

## <a name="afxregdeletekey"></a> AfxRegDeleteKey
删除指定的注册表项。  
  
### <a name="syntax"></a>语法  
  
```  
LONG AFXAPI AfxRegDeleteKey(HKEY hKey, LPCTSTR lpSubKey, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>参数  
 *hKey*  
 打开注册表项句柄。  
  
 *lpSubKey*  
 要删除的键的名称。  
  
 *pTM*  
 指向 `CAtlTransactionManager` 对象的指针。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值为 ERROR_SUCCESS。 如果函数失败，返回值是在 Winerror.h 中定义一个非零错误代码。  
  
### <a name="requirements"></a>要求  
 **标头：** afxpriv.h  

## <a name="afxregisterpreviewhandler"></a>
用于注册预览处理程序的帮助程序。  
  
### <a name="syntax"></a>语法  
  
```  
BOOL AFXAPI AfxRegisterPreviewHandler(LPCTSTR lpszCLSID, LPCTSTR lpszShortTypeName, LPCTSTR lpszFilterExt);  
```  
  
### <a name="parameters"></a>参数  
 *lpszCLSID*  
 指定处理程序的 CLSID。  
  
 *lpszShortTypeName*  
 指定处理程序的 ProgID。  
  
 *lpszFilterExt*  
 指定注册到此处理程序的文件扩展名。  
  
### <a name="requirements"></a>要求  
 **标头：** afxdisp.h   

##  <a name="atlregistertypelib"></a>  AtlRegisterTypeLib  
 调用此函数可注册类型库。  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>参数  
 *hInstTypeLib*  
 模块实例的句柄。  
  
 *lpszIndex*  
 格式字符串"\\\N"，其中 N 是类型库资源的整数索引。 如果没有索引是必需的可以为 NULL。  
  
### <a name="return-value"></a>返回值  
 返回成功，则为 S_OK 或失败时的错误 HRESULT。  
  
### <a name="remarks"></a>备注  
 使用此帮助器函数[AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)并[CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib)。  
### <a name="requirements"></a>要求  
 **标头：** atlbase.h

 ## <a name="afxregopenkey"></a> AfxRegOpenKey
 打开指定的注册表项。  
  
### <a name="syntax"></a>语法  
  
```  
LONG AFXAPI AfxRegOpenKey(HKEY hKey, LPCTSTR lpSubKey, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>参数  
 *hKey*  
 打开注册表项句柄。  
  
 *lpSubKey*  
 此函数将打开或创建的密钥的名称。  
  
 *phkResult*  
 指向一个变量来接收创建密钥的句柄的指针。  
  
 *pTM*  
 指向 `CAtlTransactionManager` 对象的指针。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值为 ERROR_SUCCESS。 如果函数失败，返回值是在 Winerror.h 中定义一个非零错误代码。  
  
### <a name="requirements"></a>要求  
 **标头：** afxpriv.h  

## <a name="afxregopenkeyex"></a>  AfxRegOpenKeyEx
打开指定的注册表项。 

### <a name="syntax"></a>语法  
  
```  
LONG AFXAPI AfxRegOpenKeyEx(HKEY hKey, LPCTSTR lpSubKey, DWORD ulOptions, REGSAM samDesired, PHKEY phkResult, CAtlTransactionManager* pTM = NULL);  
```  
  
### <a name="parameters"></a>参数  
 *hKey*  
 打开注册表项句柄。  
  
 *lpSubKey*  
 此函数将打开或创建的密钥的名称。  
  
 *ulOptions*  
 此参数保留并必须为零。  
  
 *samDesired*  
 一个屏蔽，它指定的键的所需的访问权限。  
  
 *phkResult*  
 指向一个变量来接收打开密钥的句柄的指针。  
  
 *pTM*  
 指向 `CAtlTransactionManager` 对象的指针。  
  
### <a name="return-value"></a>返回值  
 如果函数成功，返回值为 ERROR_SUCCESS。 如果函数失败，返回值是在 Winerror.h 中定义一个非零错误代码。  
  
### <a name="requirements"></a>要求  
 **标头：** afxpriv.h  

 ## <a name="afxunregisterpreviewhandler"></a> AfxUnregisterPreviewHandler
 用于注销预览处理程序的帮助程序。  
  
### <a name="syntax"></a>语法  
  
```  
BOOL AFXAPI AfxUnRegisterPreviewHandler(LPCTSTR lpszCLSID);  
```  
  
### <a name="parameters"></a>参数  
 *lpszCLSID*  
 指定要注销的处理程序的 CLSID。  
  
### <a name="requirements"></a>要求  
 **标头：** afxdisp.h  

## <a name="atlsetperuserregistration"></a> AtlSetPerUserRegistration
设置是否在应用程序将注册表访问重定向**HKEY_CURRENT_USER** (**HKCU**) 节点。  
  
### <a name="syntax"></a>语法  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>参数  
 [in]*bEnable*  
 TRUE 表示注册表信息将定向到**HKCU**节点;FALSE 表示应用程序将注册表信息写入到默认的节点。 默认的节点是**HKEY_CLASSES_ROOT** (**HKCR**)。  
  
### <a name="return-value"></a>返回值  
 如果该方法成功，则为 S_OK，否则 HRESULT 错误代码如果出现错误。  
  
### <a name="remarks"></a>备注  
 默认情况下不启用注册表重定向。 如果启用此选项时，注册表访问重定向到**HKEY_CURRENT_USER\Software\Classes**。  
  
 重定向不是全局的。 仅 MFC 和 ATL 框架受此注册表重定向。  
### <a name="requirements"></a>要求  
 **标头：** atlbase.h  

##  <a name="atlunregistertypelib"></a>  AtlUnRegisterTypeLib  
 调用此函数可注销类型库。  
  
### <a name="syntax"></a>语法  
```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib, 
    LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>参数  
 *hInstTypeLib*  
 模块实例的句柄。  
  
 *lpszIndex*  
 格式字符串"\\\N"，其中 N 是类型库资源的整数索引。 如果没有索引是必需的可以为 NULL。  
  
### <a name="return-value"></a>返回值  
 返回成功，则为 S_OK 或失败时的错误 HRESULT。  
  
### <a name="remarks"></a>备注  
 使用此帮助器函数[CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib)并[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)。  
### <a name="requirements"></a>要求  
 **标头：** atlbase.h

##  <a name="atlloadtypelib"></a>  AtlLoadTypeLib  
 调用此函数可加载类型库。  
  
### <a name="syntax"></a>语法  
```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```  
  
### <a name="parameters"></a>参数  
 *hInstTypeLib*  
 与类型库关联的模块的句柄。  
  
 *lpszIndex*  
 格式字符串"\\\N"，其中 N 是类型库资源的整数索引。 如果没有索引是必需的可以为 NULL。  
  
 *pbstrPath*  
 成功返回时，包含与该类型库相关联的模块的完整路径。  
  
 *ppTypeLib*  
 成功返回时，包含指向已加载的类型库的指针指向的指针。  
  
### <a name="return-value"></a>返回值  
 返回成功，则为 S_OK 或失败时的错误 HRESULT。  
  
### <a name="remarks"></a>备注  
 使用此帮助器函数[AtlRegisterTypeLib](#atlregistertypelib)并[AtlUnRegisterTypeLib](#atlunregistertypelib)。  
  
##  <a name="atlupdateregistryfromresourced"></a>  AtlUpdateRegistryFromResourceD  
 此函数已在 Visual Studio 2013 中弃用，并已从 Visual Studio 2015 中删除。  
  
```
<removed>
```  
  

  
##  <a name="registrydataexchange"></a>  RegistryDataExchange  
 调用此函数可在系统注册表中进行读取或写入。  

### <a name="syntax"></a>语法  
```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```  
  
### <a name="parameters"></a>参数  
 *pT*  
 指向当前对象的指针。  
  
 *rdxOp*  
 枚举值，该值指示哪个操作应在执行该函数。 请参阅允许的值的备注部分中的表。  
  
 *pItem*  
 指向要读取或写入注册表的数据。 数据还可以表示一个密钥，以从注册表中删除。 默认值为 NULL。  
  
### <a name="return-value"></a>返回值  
 返回成功，则为 S_OK 或失败时的错误 HRESULT。  
  
### <a name="remarks"></a>备注  
 宏[BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map)并[END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map)展开到调用的函数`RegistryDataExchange`。  
  
 下表中显示可能的枚举值，用于指示应执行该操作函数：  
  
|枚举值|操作|  
|----------------|---------------|  
|eReadFromReg|从注册表中读取数据。|  
|eWriteToReg|将数据写入到注册表。|  
|eDeleteFromReg|从注册表删除项。|  
  
### <a name="requirements"></a>要求  
 **标头：** atlbase.h

## <a name="see-also"></a>请参阅  
 [函数](atl-functions.md)[注册表数据交换宏](registry-data-exchange-macros.md)





