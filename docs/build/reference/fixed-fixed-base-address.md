---
title: -FIXED （固定基址） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08b1193b7cfe58aed45e4feec598a49227eafc87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374156"
---
# <a name="fixed-fixed-base-address"></a>/FIXED（固定基址）
```  
/FIXED[:NO]  
```  
  
## <a name="remarks"></a>备注  
 告知操作系统只在其首选基址加载程序。 如果不可用的首选基址，操作系统将不加载该文件。 有关详细信息，请参阅 [/BASE（基址）](../../build/reference/base-base-address.md)。  
  
 /FIXED:NO 是 DLL 的默认设置，/FIXED 是任何其他项目类型的默认设置。  
  
 指定 /FIXED，则链接不会在程序中生成重定位节。 在运行时，如果操作系统无法在指定的地址加载程序，它将发出错误消息而不会加载该程序。  
  
 指定 /fixed: no 在程序中生成重定位节。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项  
  
1.  打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../../ide/working-with-project-properties.md)。  
  
2.  选择**链接器**文件夹。  
  
3.  选择**命令行**属性页。  
  
4.  键入选项名以及在中设置**其他选项**框。  
  
### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项  
  
-   请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。  
  
## <a name="see-also"></a>请参阅  
 [设置链接器选项](../../build/reference/setting-linker-options.md)   
 [链接器选项](../../build/reference/linker-options.md)