---
title: 如何： 执行映射和减少操作并行 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cda761da013e966f91848fed01a4f96f5d373021
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685923"
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>如何：并行执行映射和减少操作

此示例演示如何使用[concurrency:: parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)和[concurrency:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)算法和[concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)类计数文件中单词的出现次数。  
  
 A*映射*操作将函数应用于序列中的每个值。 A*减少*操作将合并为一个值序列的元素。 你可以使用 c + + 标准库[std:: transform](../../standard-library/algorithm-functions.md#transform)和[std:: accumulate](../../standard-library/numeric-functions.md#accumulate)函数来执行映射和化简操作。 但是，为了提高许多问题的性能，你可以使用 `parallel_transform` 算法并行执行映射操作，并使用 `parallel_reduce` 算法并行执行化简操作。 在某些情况下，你可以使用 `concurrent_unordered_map` 以一步操作执行映射和化简。  
  
## <a name="example"></a>示例  
 以下示例计算了文件中单词出现的次数。 它使用[std:: vector](../../standard-library/vector-class.md)来表示两个文件的内容。 映射操作计算了每个向量中每个单词出现的次数。 化简操作累积了跨这两个向量的字数统计。  
  
 [!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]  
  
## <a name="compiling-the-code"></a>编译代码  
 若要编译代码，将其复制，然后将其粘贴到 Visual Studio 项目中，或将其粘贴在文件中名为`parallel-map-reduce.cpp`然后在 Visual Studio 命令提示符窗口中运行以下命令。  
  
 **cl.exe /EHsc 并行映射 reduce.cpp**  
  
## <a name="robust-programming"></a>可靠编程  
 在此示例中，你可以使用在 concurrent_unordered_map.h 中定义的 `concurrent_unordered_map` 类以一步操作执行映射和化简。  
  
 [!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]  
  
 通常情况下，你只需并行化外部或内部循环。 如果你的文件相对较少并且每个文件中包含的单词很多，则可以并行化内部循环。 如果你的文件相对较多并且每个文件中包含的单词比较少，则可以并行化外部循环。  
  
## <a name="see-also"></a>请参阅  
 [并行算法](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_transform 函数](reference/concurrency-namespace-functions.md#parallel_transform)   
 [parallel_reduce 函数](reference/concurrency-namespace-functions.md#parallel_reduce)   
 [concurrent_unordered_map 类](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
