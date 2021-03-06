---
title: 快捷键 Type 属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da825a4f2052f05b24ff724d709c7c8a4b6a3db3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645680"
---
# <a name="accelerator-type-property"></a>快捷键 Type 属性
快捷键**类型**属性确定与快捷键 ID 相关联的快捷键组合是否为虚拟键组合或 ASCII/ANSI 密钥值：  
  
-   如果**类型**属性是 ASCII[修饰符](../windows/accelerator-modifier-property.md)只能`None`或`Alt`，也可以使用的加速器**Ctrl** （由指定的密钥前面具有键`^`)。  
  
-   如果**类型**属性是 VIRTKEY 的任意组合`Modifier`和`Key`值是否有效。  
  
    > [!NOTE]
    >  如果希望快捷键对应表中输入一个值，并将值作为 ASCII/ANSI，只需单击处理**类型**表并从下拉列表中选择 ASCII 中的条目。 但是，如果您使用**键入的下一步键**命令 (**编辑**菜单) 来指定`Key`，则必须更改**类型**属性从 VIRTKEY 为 ASCII *之前*输入`Key`代码。  
  
## <a name="requirements"></a>要求  
 Win32  
  
## <a name="see-also"></a>请参阅  
 [设置快捷键属性](../windows/setting-accelerator-properties.md)   
 [快捷键编辑器](../windows/accelerator-editor.md)