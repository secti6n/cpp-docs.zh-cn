---
title: unary_negate 类 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::unary_negate
dev_langs:
- C++
helpviewer_keywords:
- unary_negate class
ms.assetid: e3b86eec-3205-49b9-ab83-f55225af4e0c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7017ee7b29e8e41e4aa33f95560a10127dc812e7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960887"
---
# <a name="unarynegate-class"></a>unary_negate 类

一种模板类，用于提供成员函数，对指定一元函数的返回值进行求反。

## <a name="syntax"></a>语法

```cpp
template <class Predicate>
class unary_negate
    : public unaryFunction<typename Predicate::argument_type, bool>
{
public:
    explicit unary_negate(const Predicate& Func);
    bool operator()(const typename Predicate::argument_type& left) const;
};
```

### <a name="parameters"></a>参数

*Func*  
 要求反的一元函数。

*left*  
 要求反的一元函数的操作数。

## <a name="return-value"></a>返回值

一元函数的求反运算。

## <a name="remarks"></a>备注

此模板类存储 _ Func 一元函数对象的副本。 它将其成员函数 `operator()` 定义为返回 **!**\_Func(left)。

很少直接使用 `unary_negate` 的构造函数。 Helper 函数 [not1](../standard-library/functional-functions.md#not1) 可提供更简单的方法，用于声明和使用 **unary_negator** 适配器谓词。

## <a name="example"></a>示例

```cpp
// functional_unary_negate.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        unary_negate<binder2nd <greater<int> > >(bind2nd(greater<int>(),10)));

    // The following helper function not1 also works for the above line
    // not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
/* Output:
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
*/
```

## <a name="requirements"></a>要求

**标头：**\<functional>

**命名空间：** std

## <a name="see-also"></a>请参阅

[C++ 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 标准库参考](../standard-library/cpp-standard-library-reference.md)<br/>
