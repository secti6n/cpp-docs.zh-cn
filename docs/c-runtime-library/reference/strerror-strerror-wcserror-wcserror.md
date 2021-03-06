---
title: strerror、_strerror、_wcserror、__wcserror | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
dev_langs:
- C++
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e89a5de45baeb9b3beea2aa538cb0a2168f3c5ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412382"
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror、_strerror、_wcserror、__wcserror

获取系统错误消息字符串 (**strerror**， **_wcserror**) 或格式化用户提供的错误消息字符串 (**_strerror**， **__wcserror**). 这些函数的更安全版本已经发布，请参阅 [strerror_s、_strerror_s、_wcserror_s、\__wcserror_s](strerror-s-strerror-s-wcserror-s-wcserror-s.md)。

## <a name="syntax"></a>语法

```C
char *strerror(
   int errnum
);
char *_strerror(
   const char *strErrMsg
);
wchar_t * _wcserror(
   int errnum
);
wchar_t * __wcserror(
   const wchar_t *strErrMsg
);
```

### <a name="parameters"></a>参数

*errnum*<br/>
错误号。

*strErrMsg*<br/>
用户提供的消息。

## <a name="return-value"></a>返回值

所有这些函数都将返回指向错误消息字符串的指针。 后续调用可覆盖该字符串。

## <a name="remarks"></a>备注

**Strerror**函数映射*errnum*为错误消息字符串并返回指向字符串的指针。 既不**strerror**也不 **_strerror**实际输出的消息： 为此，必须调用输出函数，如[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md):

```C
if (( _access( "datafile",2 )) == -1 )
   fprintf( stderr, _strerror(NULL) );
```

如果*strErrMsg*作为传递**NULL**， **_strerror**返回指向包含产生错误的最后一个库调用的系统错误消息的字符串的指针。 错误消息字符串以换行符 ('\n') 结尾。 如果*strErrMsg*是否不等于**NULL**，然后 **_strerror**将指针返回到你的字符串消息、 冒号、 一个空格、 系统错误 （按顺序） 包含的字符串生成错误，并换行字符的最后一个库调用的消息。 你的字符串消息长度最多可达 94 个字符。

实际错误数 **_strerror**变量中存储[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。 若要生成准确的结果，调用 **_strerror**库例程返回错误后立即。 否则为因为在后续调用**strerror**或 **_strerror**可以覆盖**errno**值。

**_wcserror**和 **__wcserror**宽字符版本的**strerror**和 **_strerror**分别。

**_strerror**， **_wcserror**，和 **__wcserror**不是 ANSI 定义的一部分; 它们是 Microsoft 扩展，我们建议，你并不使用它们需要可移植代码的位置。 对于 ANSI 兼容性，使用**strerror**相反。

若要获取错误字符串，我们建议**strerror**或 **_wcserror**而不是已弃用的宏[_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)和[_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)和已弃用的内部函数 **__sys_errlist**和 **__sys_nerr**。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|TCHAR.H 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcserror**|**strerror**|**strerror**|**_wcserror**|

## <a name="requirements"></a>要求

|例程|必需的标头|
|-------------|---------------------|
|**strerror**|\<string.h>|
|**_strerror**|\<string.h>|
|**_wcserror**， **__wcserror**|\<string.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅 [perror](perror-wperror.md) 示例。

## <a name="see-also"></a>请参阅

[字符串操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[perror、_wperror](perror-wperror.md)<br/>
