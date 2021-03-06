---
title: 从 ActiveX 控件向导添加类 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.class.axcontrol
dev_langs:
- C++
helpviewer_keywords:
- ActiveX Control Wizard
- Add Class from ActiveX Control Wizard [C++]
ms.assetid: 668d801c-5fb6-4176-9191-5c38995a4713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ab96943e47287c9b54753c8d3a1edb868804274
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336812"
---
# <a name="add-class-from-activex-control-wizard"></a>从 ActiveX 控件添加类向导
使用此向导从可用的 ActiveX 控件添加 MFC 类。 该向导为从所选 ActiveX 控件添加的每个接口创建类。  
  
 **添加类的位置**  
 指定从中创建类的类型库的位置。  
  
|选项|描述|  
|------------|-----------------|  
|**Registry**|在系统中注册类型库。 “可用 ActiveX 控件”中列出了已注册的类型库。|  
|**文件**|类型库不必在系统中进行注册，但必须包含在文件中。 必须在“位置”中提供文件位置。|  
  
 **可用 ActiveX 控件**  
 指定当前在系统中注册的 ActiveX 控件。 从此列表中选择一个 ActiveX 控件，以在“接口”列表中显示该控件的接口。 若要详细了解如何注册 ActiveX 控件，请参阅 [MFC ActiveX 控件：分发 ActiveX 控件](../mfc/mfc-activex-controls-distributing-activex-controls.md)。  
  
 如果单击“添加类的位置”下的“文件”，则此框无法更改。  
  
 **位置**  
 指定 ActiveX 控件的位置。 如果单击“添加类的位置”下的“文件”，可以提供包含类型库的文件的位置。 若要浏览至该文件的位置，请单击省略号按钮。  
  
 如果单击“添加类的位置”下的“注册表”，则此框无法更改。  
  
 **接口**  
 在“可用 ActiveX 控件”内当前选择的 ActiveX 控件中，或在“位置”中指定的文件内的类型库中，指定接口。  
  
|传输按钮|描述|  
|---------------------|-----------------|  
|**>**|添加当前在“接口”列表中选择的接口。 如果没有选择接口，则无法执行此操作。|  
|**>>**|在当前在“可用 ActiveX 控件”内选择的 ActiveX 控件中，或在“位置”中所指定的文件内的类型库中添加所有接口。|  
|**<**|删除当前在“生成的类”列表中选择的类。 如果当前没有在“生成的类”列表中选择类，则无法执行此操作。|  
|**<\<**|删除“生成的类”列表中的所有类。 如果“生成的类”列表为空，则无法执行此操作。|  
  
 **生成的类**  
 指定要从使用 > 或 >> 按钮添加的接口生成的类名。 可以单击此框以选择类，并使用向上键或向下键滚动该列表，查看 `Class` 框中的每个类名以及向导在你单击“完成”时生成的“.h 文件”框中的文件名。 在此框中仅能选择一个类。  
  
 可通过在此列表中选择一个类并单击 < 来删除该类。 无需在“生成的类”框中选择一个类来删除所有类；通过单击 <<，可删除“生成的类”中的所有类。  
  
 `Class`  
 指定向导在你单击“完成”时添加的“生成的类”框中选择的类的名称。 可以在 `Class` 框中编辑该名称。  
  
 **.h 文件**  
 为新项目的类的头文件设置名称。 默认情况下，此名称基于你在“生成的类”中提供的名称。 单击省略号按钮以将该文件名保存至所选择的位置，或追加到某个现有文件的类声明中。 如果选择现有文件，则向导在你单击“完成”之前都不会将其保存至所选位置。  
  
 向导不会覆盖文件。 如果选择现有文件的名称，当你单击“完成”时，向导会询问你是否要将该类声明追加至文件的内容中。 单击“是”，则追加该文件；单击“否”，则返回至向导并指定另一个文件名。  
  
 **.cpp 文件**  
 为新项目的类的实现文件设置名称。 默认情况下，此名称基于你在“生成的类”中提供的名称。 单击省略号按钮以将文件名保存到所选位置。 向导在你单击“完成”之前不会将该文件保存到所选位置。  
  
 向导不会覆盖文件。 如果选择现有文件的名称，当你单击“完成”时，向导会询问你是否要将该类实现追加至文件的内容中。 单击“是”，则追加该文件；单击“否”，则返回至向导并指定另一个文件名。  
  
## <a name="see-also"></a>请参阅  
 [从 ActiveX 控件添加类](../ide/adding-a-class-from-an-activex-control-visual-cpp.md)   
 [自动化客户端：使用类型库](../mfc/automation-clients-using-type-libraries.md)