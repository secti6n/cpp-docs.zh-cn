---
title: CMFCFontComboBox 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 67fae4e4fd130e8cb61554f7e2d41595070ee819
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852261"
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox 类
`CMFCFontComboBox`类创建包含字体列表的一个组合框控件。  
  
## <a name="syntax"></a>语法  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|构造 `CMFCFontComboBox` 对象。|  
|`CMFCFontComboBox::~CMFCFontComboBox`|析构函数。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|由框架调用以确定新项的当前字体组合框控件的已排序的列表框中的相对位置。 (重写[CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem)。)|  
|`CMFCFontComboBox::DrawItem`|由框架调用以在当前的字体组合框控件中绘制指定的项。 (重写[CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem)。)|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|检索有关当前所选字体的信息。|  
|`CMFCFontComboBox::MeasureItem`|由框架调用以通知 Windows 列表框中当前的字体组合框控件的维度。 (重写[CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem)。)|  
|`CMFCFontComboBox::PreTranslateMessage`|将窗口消息调度到之前[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)并[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 函数。 （重写 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)。）|  
|[CMFCFontComboBox::SelectFont](#selectfont)|选择符合指定的条件从字体组合框的字体。|  
|[CMFCFontComboBox::Setup](#setup)|初始化字体组合框中项的列表。|  
  
### <a name="data-members"></a>数据成员  
  
|name|描述|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|框架中，指示要使用当前的字体组合框中绘制项标签的字体。|  
  
## <a name="remarks"></a>备注  
 若要使用`CMFCFontComboBox`对象在对话框中，将添加`CMFCFontComboBox`到对话框类变量。 然后在`OnInitDialog`方法的对话框类，调用[CMFCFontComboBox::Setup](#setup)方法来初始化组合框控件中的项列表。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>要求  
 **标头：** afxfontcombobox.h  
  
##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox  
 构造 `CMFCFontComboBox` 对象。  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>返回值  
  
### <a name="remarks"></a>备注  
  
##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont  
 检索有关当前所选字体的信息。  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>返回值  
 一个指向[CMFCFontInfo 类](../../mfc/reference/cmfcfontinfo-class.md)对象，描述一种字体。 如果在组合框中不选择任何字体，它可以为 NULL。  
  
### <a name="remarks"></a>备注  
  
##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont  
 框架中，指示要使用当前的字体组合框中绘制项标签的字体。  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>备注  
 将此成员设置为 TRUE 以指示框架使用相同的字体绘制每个项的标签。 将此成员设置为 FALSE，以指示要绘制每个项的标签与名称等同于标签的字体的框架。 此成员的默认值为 FALSE。  
  
##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont  
 选择符合指定的条件从字体组合框的字体。  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>参数  
 [in]*pDesc*  
 指向字体描述对象。  
  
 [in]*lpszName*  
 指定的字体名称。  
  
 [in]*nCharSet*  
 指定字符组。 默认值为 DEFAULT_CHARSET。 有关详细信息，请参阅`lfCharSet`的成员[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)结构。  
  
### <a name="return-value"></a>返回值  
 如果字体组合框中的项匹配的说明对象指定的字体或字体名称和字符集; 则为 TRUE否则为 FALSE。  
  
### <a name="remarks"></a>备注  
 使用此方法来选择并滚动到对应于指定的字体的字体组合框中的项。  
  
### <a name="example"></a>示例  
 下面的示例演示如何使用`SelectFont`中的方法`CMFCFontComboBox`类。 此示例摘自[新的控件示例](../../visual-cpp-samples.md)。  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="setup"></a>  CMFCFontComboBox::Setup  
 初始化字体组合框中项的列表。  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>参数  
 [in]*nFontType*  
 指定字体类型。 默认值是 DEVICE_FONTTYPE、 RASTER_FONTTYPE 和 TRUETYPE_FONTTYPE 的按位组合 (OR)。  
  
 [in]*nCharSet*  
 指定字体的字符集。 默认值为 DEFAULT_CHARSET。  
  
 [in]*nPitchAndFamily*  
 指定的字体间距和系列。 默认值为 DEFAULT_PITCH。  
  
### <a name="return-value"></a>返回值  
 如果字体组合框初始化成功，则为 TRUE否则为 FALSE。  
  
### <a name="remarks"></a>备注  
 此方法通过枚举与指定的参数匹配的当前已安装的字体和字体组合框中插入这些字体名称初始化字体组合框。  
  
### <a name="example"></a>示例  
 下面的示例演示如何使用`Setup`中的方法`CMFCFontComboBox`类。 此示例摘自[新的控件示例](../../visual-cpp-samples.md)。  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>请参阅  
 [层次结构图表](../../mfc/hierarchy-chart.md)   
 [类](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox 类](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo 类](../../mfc/reference/cmfcfontinfo-class.md)
