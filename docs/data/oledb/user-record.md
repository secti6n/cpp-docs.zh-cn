---
title: 用户记录 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b53410c8116f88d51734bb302026a03994e520a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338189"
---
# <a name="user-record"></a>用户记录
用户记录提供了代码和数据结构，它表示行集列数据。 在编译时或在运行时，可以创建用户记录。 在创建使用 ATL OLE DB 提供程序的提供程序时，向导将创建如下所示 （假定你指定的"MyProvider"提供程序名称 [短名称]） 的默认用户记录：  
  
```cpp  
class CWindowsFile:  
   public WIN32_FIND_DATA  
{  
public:  
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
  
};  
```  
  
 OLE DB 提供程序模板处理所有 OLE DB 具体与客户端之间的交互。 若要获取响应所需的列数据，访问接口将调用`GetColumnInfo`函数，您必须将它们放入用户记录。 您可以显式重写`GetColumnInfo`在用户记录中，例如，通过声明它.h 文件中，如下所示：  
  
```cpp  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 这等效于：  
  
```cpp  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 此外必须实现`GetColumnInfo`用户记录的.cpp 文件中。  
  
 PROVIDER_COLUMN_MAP 宏帮助创建`GetColumnInfo`函数：  
  
-   BEGIN_PROVIDER_COLUMN_MAP 定义的函数原型和静态数组的`ATLCOLUMNINFO`结构。  
  
-   PROVIDER_COLUMN_ENTRY 定义和初始化一个`ATLCOLUMNINFO`。  
  
-   END_PROVIDER_COLUMN_MAP 关闭数组和函数。 此外可将数组元素计数放*pcCols*参数。  
  
 在运行时，创建用户记录时`GetColumnInfo`使用*pThis*参数接收指向的行集或命令实例的指针。 命令和行集必须支持`IColumnsInfo`接口，因此可以从该指针获取列信息。  
  
 `CommandClass` 和`RowsetClass`是命令，并使用用户记录的行集。  
  
 有关如何重写的更详细的示例`GetColumnInfo`中的用户记录，请参阅[动态确定返回给使用者列](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)。  
  
## <a name="see-also"></a>请参阅  
 [OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)