---
title: wctrans | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wctrans
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wctrans
dev_langs:
- C++
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 613c3c64885f10029a8b013504d84ffa8f35d664
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410484"
---
# <a name="wctrans"></a>wctrans

确定一组字符代码到另一组之间的映射。

## <a name="syntax"></a>语法

```C
wctrans_t wctrans(
   const char *property
);
```

### <a name="parameters"></a>参数

*属性*<br/>
指定一个有效转换的字符串。

## <a name="return-value"></a>返回值

如果**LC_CTYPE**当前区域设置类别的未定义其名称与属性的字符串匹配的映射*属性*，函数将返回零。 否则，它将返回一个适合用作对 [towctrans](towctrans.md) 的后续调用的第二个参数的非零值。

## <a name="remarks"></a>备注

此函数确定一组字符代码到另一组之间的映射。

以下调用对在所有区域设置中具有相同的行为（但可以定义其他映射，甚至在“C”区域设置中）：

|函数|与以下项相同|
|--------------|-------------|
|tolower(c)|towctrans (c、 wctrans("towlower"))|
|towupper(c)|towctrans (c、 wctrans("toupper"))|

## <a name="requirements"></a>要求

|例程|必需的标头|
|-------------|---------------------|
|**wctrans**|\<wctype.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_wctrans.cpp
// compile with: /EHsc
// This example determines a mapping from one set of character
// codes to another.

#include <wchar.h>
#include <wctype.h>
#include <stdio.h>
#include <iostream>

int main()
{
    wint_t c = 'a';
    printf_s("%d\n",c);

    wctrans_t i = wctrans("toupper");
    printf_s("%d\n",i);

    wctrans_t ii = wctrans("towlower");
    printf_s("%d\n",ii);

    wchar_t wc = towctrans(c, i);
    printf_s("%d\n",wc);
}
```

```Output
97
1
0
65
```

## <a name="see-also"></a>请参阅

[数据转换](../../c-runtime-library/data-conversion.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
