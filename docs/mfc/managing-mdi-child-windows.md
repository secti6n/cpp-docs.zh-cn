---
title: 管理 MDI 子窗口 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MDICLIENT
dev_langs:
- C++
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58ddef11e56da760bbecaa47f03dfa6c57dfa3ed
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929476"
---
# <a name="managing-mdi-child-windows"></a>管理 MDI 子窗口
MDI 主框架窗口 （每个应用程序一个） 包含一个称作 MDICLIENT 窗口的特殊子窗口。 MDICLIENT 窗口管理主框架窗口的工作区，并且其自身具有子窗口： 派生自的文档窗口`CMDIChildWnd`。 由于文档窗口是框架窗口（MDI 子窗口），因此它们也有其自己的子级。 在所有这些情况下，父窗口管理其子窗口并将一些命令转发给它们。  
  
 在 MDI 框架窗口中，框架窗口管理 MDICLIENT 窗口中，其进行重新定位控件条结合。 MDICLIENT 窗口中，反过来，管理所有 MDI 子框架窗口。 下图显示 MDI 框架窗口、 其 MDICLIENT 窗口中与其子文档框架窗口之间的关系。  
  
 ![MDI 框架窗口中的子窗口](../mfc/media/vc37gb1.gif "vc37gb1")  
MDI 框架窗口和子窗口  
  
 MDI 框架窗口还将与当前 MDI 子窗口（如果有一个）结合使用。 MDI 框架窗口在尝试处理命令消息之前，会将这些消息委派给 MDI 子窗口。  
  
## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么  
  
-   [创建文档框架窗口](../mfc/creating-document-frame-windows.md)  
  
-   [框架窗口样式](../mfc/frame-window-styles-cpp.md)  
  
## <a name="see-also"></a>请参阅  
 [使用框架窗口](../mfc/using-frame-windows.md)

