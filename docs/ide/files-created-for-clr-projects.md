---
title: 为 CLR 项目创建的文件 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9d66c3f55164a743bc395dc5e9b48f8bcd57654
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334660"
---
# <a name="files-created-for-clr-projects"></a>为 CLR 项目创建的文件
使用 Visual C++ 模板创建项目时，会创建多个文件，具体取决于使用的模板。 下表列出了由 .NET Framework 项目的项目模板创建的所有文件。  
  
|文件名|文件说明|  
|---------------|----------------------|  
|AssemblyInfo.cpp|其中包含用于修改项目程序集元数据的信息（即属性、文件、资源、类型、版本信息、签名信息等）的文件。 有关详细信息，请参阅[程序集概念](/dotnet/framework/app-domains/assembly-contents)。|  
|projname.asmx|一个引用封装了 XML Web 服务功能的托管类的文本文件。|  
|projname.cpp|Visual Studio 为你创建的主要源文件和应用程序的入口点。 标识项目 .dll 文件和项目命名空间。 在此文件中提供你自己的代码。|  
|projname.vsdisco|XML 部署文件，其中包含指向描述 XML Web 服务的其他资源的链接。|  
|projname.h|项目的主要包含文件，其中包含所有声明、全局符号和其他头文件的 `#include` 指令。|  
|projname.sln|开发环境中用于将项目的所有元素整理到单个解决方案中的解决方案文件。|  
|projname.suo|开发环境中使用的解决方案选项文件。|  
|projname.vcxproj|开发环境中使用的项目文件，用于存储特定于此项目的信息。|  
|ReadMe.txt|一个使用模板创建的实际文件名描述项目中每个文件的文件。|