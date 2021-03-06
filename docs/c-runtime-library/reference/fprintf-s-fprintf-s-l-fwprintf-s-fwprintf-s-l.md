---
title: fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fprintf_s_l
- fwprintf_s
- fprintf_s
- _fwprintf_s_l
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
apitype: DLLExport
f1_keywords:
- _ftprintf_s
- fprintf_s
- fwprintf_s
dev_langs:
- C++
helpviewer_keywords:
- ftprintf_s_l function
- ftprintf_s function
- _fprintf_s_l function
- _ftprintf_s function
- _ftprintf_s_l function
- fwprintf_s_l function
- fwprintf_s function
- fprintf_s_l function
- fprintf_s function
- _fwprintf_s_l function
- print formatted data to streams
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea8e9d28a960149d0f199b090daa98e76049f291
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404212"
---
# <a name="fprintfs-fprintfsl-fwprintfs-fwprintfsl"></a>fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l

将格式化数据输出到流。 如 [CRT 中的安全功能](../../c-runtime-library/security-features-in-the-crt.md)中所述，这些版本的 [fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md) 具有安全增强功能。

## <a name="syntax"></a>语法

```C
int fprintf_s(
   FILE *stream,
   const char *format [,
   argument_list ]
);
int _fprintf_s_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument_list ]
);
int fwprintf_s(
   FILE *stream,
   const wchar_t *format [,
   argument_list ]
);
int _fwprintf_s_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument_list ]
);
```

### <a name="parameters"></a>参数

*流*<br/>
指向**文件**结构的指针。

*format*<br/>
窗体控件字符串。

*argument_list*<br/>
格式字符串的可选自变量。

*locale*<br/>
要使用的区域设置。

## <a name="return-value"></a>返回值

**fprintf_s**返回写入的字节数。 **fwprintf_s**返回写入的宽字符数。 其中每个函数在出现输出错误时返回一个负值。

## <a name="remarks"></a>备注

**fprintf_s**格式和输出一系列字符和值输出到*流*。 在每个自变量*argument_list* （如果有） 进行转换和输出中的相应格式规范根据*格式*。 *格式*自变量使用[格式规范语法 printf 和 wprintf 函数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)。

**fwprintf_s**是宽字符版本的**fprintf_s**; 在**fwprintf_s**，*格式*是宽字符字符串。 如果在 ANSI 模式下打开流，则这些函数行为相同。 **fprintf_s**当前不支持输出到 UNICODE 流。

使用这些函数的版本 **_l**后缀是相同，只不过它们使用传递而不是当前区域设置的区域设置参数。

> [!IMPORTANT]
> 确保 format 不是用户定义的字符串。

如不安全版本 (请参阅[fprintf、 _fprintf_l、 fwprintf、 _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md))，这些函数验证其参数和中所述将调用无效参数处理程序，[参数验证](../../c-runtime-library/parameter-validation.md)，如果任一*流*或*格式*是 null 指针。 格式字符串本身也需进行验证。 如果有任何未知或格式错误的格式化说明符，则这些函数将生成无效参数异常。 在所有情况下，如果允许执行继续，则函数返回-1 并设置**errno**到**EINVAL**。 有关这些代码以及其他错误代码的详细信息，请参阅 [_doserrno、errno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|TCHAR.H 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftprintf_s**|**fprintf_s**|**fprintf_s**|**fwprintf_s**|
|**_ftprintf_s_l**|**_fprintf_s_l**|**_fprintf_s_l**|**_fwprintf_s_l**|

有关更多信息，请参见 [格式规范](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)。

## <a name="requirements"></a>要求

|函数|必需的标头|
|--------------|---------------------|
|**fprintf_s**， **_fprintf_s_l**|\<stdio.h>|
|**fwprintf_s**， **_fwprintf_s_l**|\<stdio.h> 或 \<wchar.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_fprintf_s.c
// This program uses fprintf_s to format various
// data and print it to the file named FPRINTF_S.OUT. It
// then displays FPRINTF_S.OUT on the screen using the system
// function to invoke the operating-system TYPE command.

#include <stdio.h>
#include <process.h>

FILE *stream;

int main( void )
{
   int    i = 10;
   double fp = 1.5;
   char   s[] = "this is a string";
   char   c = '\n';

   fopen_s( &stream, "fprintf_s.out", "w" );
   fprintf_s( stream, "%s%c", s, c );
   fprintf_s( stream, "%d\n", i );
   fprintf_s( stream, "%f\n", fp );
   fclose( stream );
   system( "type fprintf_s.out" );
}
```

```Output
this is a string
10
1.500000
```

## <a name="see-also"></a>请参阅

[流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_cprintf、_cprintf_l、_cwprintf、_cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fscanf、_fscanf_l、fwscanf、_fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
