---
title: 欢迎回到 C++ （现代 C++） |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c4426f3d25681e3ee46bf4d5da615d185babb0f0
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462357"
---
# <a name="welcome-back-to-c-modern-c"></a>欢迎回到 C++（现代 C++）
C++ 是世界上最常用的编程语言之一。 正确编写的 C++ 程序是快速而高效的。 该语言比其他语言更加灵活，因为你可以使用它来创建各种应用程序——从有趣而刺激的游戏，到高性能的科学软件、设备驱动程序、嵌入式程序和 Windows 客户端应用。 20 多年来，人们使用 C++ 解决此类问题和许多其他问题。 你可能不知道，越来越多的 C++ 程序员已经抛弃了过时的 C 样式编程，转而使用使用现代 C++。   
  
 C++ 最初的要求之一，就是要向后兼容 C 语言。 从那时起，C++ 经历了几代演变，从带有类的 C 语言发展到原始的 C++ 语言规范，再到后来的许多改进。 由于有此传承，C++ 通常称为多范式编程语言。 在 C++ 中，可进行纯过程式 C 样式编程，此类编程样式涉及裸指针、裸数组、以 NULL 结尾的字符串、自定义数据结构，以及其他在可能实现卓越性能的同时也可能产生 Bug 和导致复杂性的功能。  由于 C 样式编程充满此类风险，因此 C++ 的一个目标就是使程序在确保类型安全的同时，更易于编写、扩展和维护。 在早期，C++ 倡导面向对象的编程等编程范式。 随着时代变迁，语言设计者在为此语言加入许多功能的同时，也加入了经过大量测试的标准数据结构和算法库。 正是这些改进，使得实现现代 C++ 样式成为可能。   
  
 现代 C++ 强调：  
  
-   使用基于堆栈的作用域，而非堆或静态全局作用域。  
  
-   使用自动类型推理，而非显式类型名称。  
  
-   使用智能指针，而非裸指针。  
  
-   使用 `std::string` 和 `std::wstring` 类型（请参阅[\<string>](../standard-library/string.md)）而不是裸的 `char[]` 数组。  
  
-   使用诸如`vector`、`list`、`map` 之类的 [C++ 标准库](../standard-library/cpp-standard-library-header-files.md)容器，而不是裸数组或手工编写的容器。 请参阅[\<vector>](../standard-library/vector.md)， [\<list>](../standard-library/list.md)和[\<map >](../standard-library/map.md)。  
  
-   使用 C++ 标准库[算法](../standard-library/algorithm.md)而非手动编写的算法来实现。  
  
-   使用异常来报告和处理错误条件。  
  
-   使用 C++ 标准库的`std::atomic<>`(请参阅[\<atomic >](../standard-library/atomic.md)) 进行无锁的线程间通信，而不是其他线程间通信机制。  
  
-   使用内联的 [lambda 函数](../cpp/lambda-expressions-in-cpp.md)而不是单独实现的小函数。  
  
-   使用基于范围的 for 循环，可以编写更可靠的循环形式。即，使用`for ( for-range-declaration : expression )` 形式来遍历数组、 C++ 标准库容器和 Windows 运行时集合。 这是 Core 语言支持的一部分。 有关详细信息，请参阅[基于范围的 for 语句 (C++)](../cpp/range-based-for-statement-cpp.md)。  
  
 C++ 语言本身也有所发展。 比较以下代码片段。 下面显示了过去 C++ 的代码片段：  
  
```cpp  
#include <vector>

void f()
{
    // Assume circle and shape are user-defined types  
    circle* p = new circle( 42 );   
    vector<shape*> v = load_shapes();  

    for( vector<circle*>::iterator i = v.begin(); i != v.end(); ++i ) {  
        if( *i && **i == *p )  
            cout << **i << " is a match\n";  
    }  

    // CAUTION: If v's pointers own the objects, then you
    // must delete them all before v goes out of scope.
    // If v's pointers do not own the objects, and you delete
    // them here, any code that tries to dereference copies
    // of the pointers will cause null pointer exceptions.
    for( vector<circle*>::iterator i = v.begin();  
            i != v.end(); ++i ) {  
        delete *i; // not exception safe  
    }  

    // Don't forget to delete this, too.  
    delete p;  
} // end f()
```

 以下是用现代 C++ 完成同一操作的代码片段：  
  
```cpp
#include <memory>  
#include <vector>  

void f()
{
    // ...  
    auto p = make_shared<circle>( 42 );  
    vector<shared_ptr<shape>> v = load_shapes();  

    for( auto& s : v ) 
    {  
        if( s && *s == *p )
        {
            cout << *s << " is a match\n";
        }
    }
}
```

 在现代 C++ 中，不必使用 new/delete 或显式异常处理程序，因为可以使用智能指针来替代 当你使用**自动**的类型推断并[lambda 函数](../cpp/lambda-expressions-in-cpp.md)，可以编写代码更快，加强代码并更好地了解。 基于范围的并**有关**循环是更简洁、 更易于使用，和不太容易发生意外错误比 C 样式**为**循环。 可以使用样板来尽量减少编写应用所需的代码行数。 
 确保代码能够安全地处理异常和内存，无需进行内存分配/释放或错误码的处理。  
  
 现代 C++ 整合了两种多态性：通过模板实现的编译时多态性，以及通过继承和虚拟化实现的运行时多态性。 可以结合使用这两种多态性以增强效果。 C++ 标准库模板 `shared_ptr` 可以相当轻松地通过内部的虚函数进行类型擦除。 但当模板是更好的选择时，请不要过度使用虚拟化来实现多态性。 模板其实很强大。  
  
 如果你是从其他语言（尤其是以引用类型为主而值类型很少的托管语言）转到 C++ 的，请注意，C++ 类在默认情况下都是值类型。 但是，你可以将这些 C++ 类指定为引用类型，从而实现支持面向对象的编程的多态行为。 另请注意，值类型偏重内存和布局控制，引用类型偏重支持多态性的基类和虚函数。 默认情况下，值类型是可复制的，即每个值类型都有一个复制构造函数和一个复制赋值运算符。 在指定引用类型时，请将类设为不可复制（禁用复制构造函数和复制赋值运算符），并通过虚析构函数来启用多态性。 值类型还与内容相关。复制值类型的值以后，会产生两个独立的、内容可分别修改的值。 引用类型则与标识（对象是什么种类）相关，因此引用类型有时称为多态类型。  
  
 C++ 正在复兴，因为功能再次占据首要位置。 当程序员的工作效率很重要时，Java 和 C# 等语言是很好的选择；但当功能和性能至关重要时，此类语言就暴露出了自身限制。 在实现高效率和强大功能（特别是在硬件有限的设备上）方面，现代 C++ 无可匹敌。  
  
 不仅语言现代，开发工具也很现代。 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 可让开发周期的各个部分高效可靠。 开发周期包括应用程序生命周期管理 (ALM) 工具、IntelliSense 等 IDE 增强功能、XAML 等适用于工具的机制，以及生成、调试和许多其他工具。  
  
 此部分文档中的文章提供了有关在编写现代 C++ 程序时最重要的功能和技术的深入指导与最佳做法。  
  
-   [C++ 类型系统](../cpp/cpp-type-system-modern-cpp.md)  
  
-   [统一初始化和委派构造函数](../cpp/uniform-initialization-and-delegating-constructors.md)  
  
-   [对象生存期和资源管理](../cpp/object-lifetime-and-resource-management-modern-cpp.md)  
  
-   [对象拥有资源 （RAII）](../cpp/objects-own-resources-raii.md)  
  
-   [智能指针](../cpp/smart-pointers-modern-cpp.md)  
  
-   [用于编译时封装的 Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)  
  
-   [容器](../cpp/containers-modern-cpp.md)  
  
-   [算法](../cpp/algorithms-modern-cpp.md)  
  
-   [字符串和 I/O 格式化 （现代 C++）](../cpp/string-and-i-o-formatting-modern-cpp.md)  
  
-   [错误和异常处理](../cpp/errors-and-exception-handling-modern-cpp.md)  
  
-   [ABI 边界处的可移植性](../cpp/portability-at-abi-boundaries-modern-cpp.md)  
  
 有关详细信息，请参阅 StackOverflow 文章[哪些 C++ 用法在 C++ 11 中已经弃用用](http://go.microsoft.com/fwlink/p/?linkid=402836)  
  
## <a name="see-also"></a>请参阅  
 [C++ 语言参考](../cpp/cpp-language-reference.md)   
 [Lambda 表达式](../cpp/lambda-expressions-in-cpp.md)   
 [C++ 标准库](../standard-library/cpp-standard-library-reference.md)  
 [Visual C++ 语言一致性](../visual-cpp-language-conformance.md)  