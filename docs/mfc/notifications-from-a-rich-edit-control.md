---
title: 通知来自 Rich Edit 控件 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 928728093ff6e2150578c4ba48f2d8081620a48d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931139"
---
# <a name="notifications-from-a-rich-edit-control"></a>来自 Rich Edit 控件的通知
通知消息事件影响 rich edit 控件的报表 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 它们可由父窗口的处理或者，可使用消息反射被 rich edit 控件本身的方法。 Rich edit 控件支持的所有使用与编辑控件，以及几个附加的通知消息。 你可以确定哪些通知消息 rich edit 控件发送其父窗口通过设置其"事件掩码"。  
  
 若要设置的事件掩码为 rich edit 控件，使用[SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask)成员函数。 你可以检索当前事件掩码 rich edit 控件通过使用[GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask)成员函数。  
  
 以下各段列出几个特定的通知和其用途：  
  
-   EN_MSGFILTER 处理 EN_MSGFILTER 通知允许类，或者 rich edit 控件或其父窗口时，筛选所有键盘和鼠标输入到控件。 处理程序可以防止键盘或鼠标消息正在处理或可以通过修改指定更改消息[MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936)结构。  
  
-   EN_PROTECTED 处理 EN_PROTECTED 通知消息，以检测当用户尝试修改受保护的文本。 要为受保护，将标记的文本范围，则可以将受保护的字符效果的设置。 有关详细信息，请参阅[Rich Edit 控件中的字符格式](../mfc/character-formatting-in-rich-edit-controls.md)。  
  
-   EN_DROPFILES 你可以使用户能够通过处理 EN_DROPFILES 通知消息放在 rich edit 控件中的文件。 指定[ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895)结构包含正在删除的文件信息。  
  
-   当前所选内容更改通过处理 EN_SELCHANGE 通知消息时，可以检测 EN_SELCHANGE 应用程序。 通知消息指定[SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952)结构，它包含有关新选择信息。  
  
## <a name="see-also"></a>请参阅  
 [使用 CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [控件](../mfc/controls-mfc.md)

