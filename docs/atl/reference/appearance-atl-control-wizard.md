---
title: 外观，ATL 控件向导 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3dd95e3e25cd015fd326c236f15a965e3fb9e801
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025875"
---
# <a name="appearance-atl-control-wizard"></a>外观，ATL 控件向导
在此处插入摘要的"搜索结果"。  
  
 在向导的此页用于标识控件的其他用户元素选项。 此页将标识为控件的可用**标准控件**下**控件类型**上[选项，ATL 控件向导](../../atl/reference/options-atl-control-wizard.md)页。  
  
## <a name="uielement-list"></a>UIElement 列表  
**查看状态**  
设置容器内控件的外观。  
  
 -   **不透明**： 设置位 VIEWSTATUS_OPAQUE [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)枚举和绘制整个控件矩形传递给[CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw)方法。 显示完全不透明的该控件和容器的任何控件边界后面显示。      
      
        此设置有助于更快地绘制控件的容器。 如果未选择此选项，该控件可以包含透明部分。  
      
        仅一个不透明控件可以具有纯背景。  
      
 -   设置 VIEWSTATUS_SOLIDBKGND 位 VIEWSTATUS 枚举中。 控件的背景显示为具有无模式的纯色。  
      
  此选项才可用才**不透明**还选择选项。  
  
**添加的控件**  
设置要通过添加基于 Windows 控件类型的控件[CContainedWindow](ccontainedwindowt-class.md)数据成员添加到实现该控件的类。 它还会添加消息映射和消息处理程序函数来处理控件的 Windows 消息。 从列表中选择你想要创建，如果有 Windows 控件的类型。  

 -   `Button`  
      
 -   `ListBox`  
      
 -   `SysAnimate32`  
      
 -   `SysListView32`  
      
 -   `ComboBox`  
      
 -   `RichEdit`  
      
 -   `SysDateTimePick32`  
      
 -   `SysMonthCal32`  
      
 -   `ComboBoxEx32`  
      
 -   `ScrollBar`  
      
 -   `SysHeader32`  
      
 -   `SysTabControl32`  
      
 -   `Edit`  
      
 -   `Static`  
      
 -   `SysIPAddress32`  
      
 -   `SysTreeView32`  
  
**杂项状态**  
设置控件的其他外观和行为选项。  
  
 -   **在运行时不可见**： 设置要在运行时不可见的控件。 不可见的控件可用于在后台，如时间间隔内触发事件执行操作。  
      
 -   **作用类似于按钮**： 设置位 OLEMISC_ACTSLIKEBUTTON [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497)枚举，以使控件执行操作就像按钮一样。 如果容器已标记为默认按钮的控件的客户端站点，选择此选项可使按钮控件以将它用较粗的框架绘制自身显示为默认按钮。 请参阅[CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault)有关详细信息。  
      
  -   **作用类似于标签**： 设置 OLEMISC_ACTSLIKELABEL 位 OLEMISC 枚举中以启用要替换容器的本机标签控件。 容器确定应如何处理此标志，如果任何内容。  
  
**其他**  
设置控件的其他行为选项。  
  
 -   **规范化 DC**： 设置要调用以绘制自身时创建正常化的设备上下文的控件。 此操作标准化控件的外观，但使绘制效率较低。  
      
 -   **仅适用于窗口**： 指定控件不能为无窗口。 如果不选择此选项，你的控件是支持无窗口对象的容器中无自动窗口和自动为有窗口不支持无窗口对象的容器中。 选择此选项将强制控件有窗口的即使在支持无窗口对象的容器中。  
      
 -   **可插入**： 选择此选项可使控件在出现**插入对象**Word 和 Excel 等应用程序对话框。 然后可以由任何应用程序支持通过此对话框中的嵌入的对象插入您的控件。  
  
## <a name="see-also"></a>请参阅  
 [ATL 控件向导](../../atl/reference/atl-control-wizard.md)   
 [SUBEDIT 示例： 超类的标准 Windows 控件](http://msdn.microsoft.com/30e46bdc-ed92-417c-b6b8-359017265a7b)

