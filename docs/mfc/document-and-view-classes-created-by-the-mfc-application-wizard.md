---
title: 文档和查看 MFC 应用程序向导创建的类 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b83886784970492da0c5e2a335dbe08119ecaae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349917"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC 应用程序向导创建的文档和视图类
MFC 应用程序向导为您创建了主干文档和视图类，从而让您在程序开发中抢占先机。 然后，你可以[将命令和消息映射到这些类](../mfc/reference/mapping-messages-to-functions.md)并使用 Visual c + + 源代码编辑器编写其成员函数。  
  
 MFC 应用程序向导创建的文档类派生自类[CDocument](../mfc/reference/cdocument-class.md)。 视图类派生自[CView](../mfc/reference/cview-class.md)。 应用程序向导为这些类提供的名称以及包含这些类的文件基于您在“应用程序向导”对话框中提供的项目名称。 在应用程序向导中，您可以使用“生成的类”页修改默认名称。  
  
 某些应用程序可能需要多个文档类、视图类或框架窗口类。 有关详细信息，请参阅[多文档类型、 视图和框架窗口](../mfc/multiple-document-types-views-and-frame-windows.md)。  
  
## <a name="see-also"></a>请参阅  
 [文档/视图体系结构](../mfc/document-view-architecture.md)

