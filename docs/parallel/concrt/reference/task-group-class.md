---
title: task_group 类 |Microsoft Docs
ms.custom: ''
ms.date: 07/20/2018
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_group
- PPL/concurrency::task_group
- PPL/concurrency::task_group::task_group
dev_langs:
- C++
helpviewer_keywords:
- task_group class
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33b285cb55e04bcae2fd7f65ef5e94686e88e5e6
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208983"
---
# <a name="taskgroup-class"></a>task_group 类
`task_group` 类表示可以等待或取消的并行工作的集合。  
  
## <a name="syntax"></a>语法  
  
```  
class task_group;  
```  
  
## <a name="members"></a>成员  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[task_group](#ctor)|已重载。 构造一个新`task_group`对象。|  
|[~ task_group 析构函数](#dtor)|销毁 `task_group` 对象。 你应该调用`wait`或`run_and_wait`析构函数在执行之前，除非析构函数执行堆栈展开因异常而产生的对象上的方法。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[取消](#cancel)|可以最大努力尝试取消的子树的根节点的此任务组的工作。 对任务组计划每个任务都将获取取消间接在可能的情况。|  
|[is_canceling](#is_canceling)|通知调用方任务组当前正在取消操作。 这不一定表示的`cancel`上调用了方法`task_group`对象 (尽管这样肯定会让此方法以返回`true`)。 它可能发生此情况的`task_group`对象正在执行内联和任务组进一步向上工作树中已取消。 在这些位置等的情况下运行时可以确定取消将流过提前`task_group`对象，`true`也将返回。|  
|[run](#run)|已重载。 在计划任务`task_group`对象。 如果`task_handle`对象作为参数传递`run`，调用方负责管理的生存期`task_handle`对象。 性能比使用采用对引用的版本较低版本将对函数对象的引用作为参数涉及在运行时这可能是堆分配的方法`task_handle`对象。 采用参数 `_Placement` 的版本导致任务偏向在该参数指定的位置执行。|  
|[run_and_wait](#run_and_wait)|已重载。 计划任务以运行内联将在调用上下文的帮助下`task_group`完整的取消支持的对象。 然后函数等待直到上的所有工作`task_group`对象已完成或已取消。 如果`task_handle`对象作为参数传递`run_and_wait`，调用方负责管理的生存期`task_handle`对象。|  
|[等待](#wait)|等待，直到上的所有工作`task_group`对象已完成或已取消。|  
  
## <a name="remarks"></a>备注  
 与严格限制不同`structured_task_group`类，`task_group`类是更普遍的构造。 它不具有任何所描述的限制[structured_task_group](structured-task-group-class.md)。 `task_group` 对象可能会安全地在线程之间使用和利用自由的方式。 缺点`task_group`构造是可能无法执行以及`structured_task_group`构造的任务的执行少量的工作。  
  
 有关详细信息，请参阅[任务并行](../task-parallelism-concurrency-runtime.md)。  
  
## <a name="inheritance-hierarchy"></a>继承层次结构  
 `task_group`  
  
## <a name="requirements"></a>要求  
 **标头：** ppl.h  
  
 **命名空间：** 并发  
  
##  <a name="cancel"></a> 取消 

 可以最大努力尝试取消的子树的根节点的此任务组的工作。 对任务组计划每个任务都将获取取消间接在可能的情况。  
  
```  
void cancel();  
```  
  
### <a name="remarks"></a>备注  
 有关详细信息，请参阅[取消](../cancellation-in-the-ppl.md)。  
  
##  <a name="is_canceling"></a> is_canceling 

 通知调用方任务组当前正在取消操作。 这不一定表示的`cancel`上调用了方法`task_group`对象 (尽管这样肯定会让此方法以返回`true`)。 它可能发生此情况的`task_group`对象正在执行内联和任务组进一步向上工作树中已取消。 在这些位置等的情况下运行时可以确定取消将流过提前`task_group`对象，`true`也将返回。  
  
```  
bool is_canceling();  
```  
  
### <a name="return-value"></a>返回值  
 指示是否`task_group`对象是否正在取消操作 （或保证可稍后）。  
  
### <a name="remarks"></a>备注  
 有关详细信息，请参阅[取消](../cancellation-in-the-ppl.md)。  
  
##  <a name="run"></a> 运行 

 在计划任务`task_group`对象。 如果`task_handle`对象作为参数传递`run`，调用方负责管理的生存期`task_handle`对象。 性能比使用采用对引用的版本较低版本将对函数对象的引用作为参数涉及在运行时这可能是堆分配的方法`task_handle`对象。 采用参数 `_Placement` 的版本导致任务偏向在该参数指定的位置执行。  
  
```  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func  
);  
  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func,  
   location& _Placement  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle,  
   location& _Placement  
);  
```  
  
### <a name="parameters"></a>参数  
 `_Function`  
 将调用以执行任务句柄的主体的函数对象的类型。  
  
 `_Func`  
 一个函数，它将调用以调用任务正文。 这可能是 lambda 表达式或其他对象，支持具有签名的函数调用运算符的版本`void operator()()`。  
  
 `_Placement`  
 对应执行 `_Func` 参数所表示任务的位置的引用。  
  
 `_Task_handle`  
 句柄正在计划的工作。 请注意，调用方负责此对象的生存期。 在运行时将继续期望其存留，直至`wait`或`run_and_wait`对此调用方法`task_group`对象。  
  
### <a name="remarks"></a>备注  
 运行时计划提供的工作函数，以在更高版本时，可以是在调用函数返回之后运行。 此方法使用[task_handle](task-handle-class.md)对象来保存一份提供工作函数。 因此，将传递给此方法的函数对象中发生的任何状态更改不会在该函数对象的副本中。 此外，请确保通过指针或引用此工作函数传递任何对象的生存期保持有效，直到工作函数返回。  
  
 如果`task_group`因堆栈展开从异常的结果，您不需要保证，已调用为`wait`或`run_and_wait`方法。 在这种情况下，析构函数将相应地取消并等待由任务`_Task_handle`参数来完成。  
  
 该方法将引发[invalid_multiple_scheduling](invalid-multiple-scheduling-class.md)如果该任务处理的异常由给定`_Task_handle`参数已安排到通过任务组对象上`run`方法而且已进行了任何干预调用为`wait`或`run_and_wait`任务组上的方法。  
  
##  <a name="run_and_wait"></a> run_and_wait 

 计划任务以运行内联将在调用上下文的帮助下`task_group`完整的取消支持的对象。 然后函数等待直到上的所有工作`task_group`对象已完成或已取消。 如果`task_handle`对象作为参数传递`run_and_wait`，调用方负责管理的生存期`task_handle`对象。  
  
```  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   const _Function& _Func  
);  
```  
  
### <a name="parameters"></a>参数  
 `_Function`  
 将调用以执行任务主体的函数对象的类型。  
  
 `_Task_handle`  
 句柄将在调用上下文以内联方式运行的任务。 请注意，调用方负责此对象的生存期。 在运行时将继续期望其存留，直至`run_and_wait`方法完成执行。  
  
 `_Func`  
 一个函数，它将调用以调用该工作的正文。 这可能是 lambda 表达式或其他对象，支持具有签名的函数调用运算符的版本`void operator()()`。  
  
### <a name="return-value"></a>返回值  
 指示是否满足该等待或任务组已取消，因显式取消操作或从其任务之一所引发的异常。 有关详细信息，请参阅[task_group_status](concurrency-namespace-enums.md#task_group_status)。  

  
### <a name="remarks"></a>备注  
 请注意，其中一个或多个任务安排到`task_group`对象可能会将在调用上下文中执行内联。  
  
 如果一个或多个与此计划的任务`task_group`对象引发了异常，运行时将选择其选择的一个此类异常，并将其传播到调用`run_and_wait`方法。  
  
 从返回时`run_and_wait`方法`task_group`对象时，运行时将对象重置为干净状态可以重复使用它。 这包括用例其中`task_group`对象已被取消。  
  
 在执行非异常路径，具有一定要这样做来调用此方法或`wait`方法之前的析构函数`task_group`执行。  
  
##  <a name="ctor"></a> task_group 

 构造一个新`task_group`对象。  
  
```  
task_group();  
  
task_group(  
   cancellation_token _CancellationToken  
);  
```  
  
### <a name="parameters"></a>参数  
 `_CancellationToken`  
 与此任务组相关联的取消标记。 取消标记时，也将取消此任务组。  
  
### <a name="remarks"></a>备注  
 采用取消标记的构造函数会创建一个在取消与标记相关联的源时将会取消的 `task_group`。 提供显式取消标记也可以避免此任务组参与采用不同标记或没有标记的父组的隐式取消。  
  
##  <a name="dtor"></a> ~ task_group 

 销毁 `task_group` 对象。 你应该调用`wait`或`run_and_wait`析构函数在执行之前，除非析构函数执行堆栈展开因异常而产生的对象上的方法。  
  
```  
~task_group();  
```  
  
### <a name="remarks"></a>备注  
 如果析构函数导致正常执行过程中 （例如，不堆栈展开由于出现异常） 以及既不运行`wait`也不`run_and_wait`在调用方法、 析构函数可能会引发[missing_wait](missing-wait-class.md)异常。  
  
##  <a name="wait"></a> 等待 

 等待，直到上的所有工作`task_group`对象已完成或已取消。  
  
```  
task_group_status wait();  
```  
  
### <a name="return-value"></a>返回值  
 指示是否满足该等待或任务组已取消，因显式取消操作或从其任务之一所引发的异常。 有关详细信息，请参阅[task_group_status](concurrency-namespace-enums.md#task_group_status)。  

  
### <a name="remarks"></a>备注  
 请注意，其中一个或多个任务安排到`task_group`对象可能会将在调用上下文中执行内联。  
  
 如果一个或多个与此计划的任务`task_group`对象引发了异常，运行时将选择其选择的一个此类异常，并将其传播到调用`wait`方法。  
  
 调用`wait`上`task_group`对象将其重置为空白状态可以重复使用它。 这包括用例其中`task_group`对象已被取消。  
  
 在执行非异常路径，具有一定要这样做来调用此方法或`run_and_wait`方法之前的析构函数`task_group`执行。  
  
## <a name="see-also"></a>请参阅  
 [并发 Namespace](concurrency-namespace.md)   
 [structured_task_group 类](structured-task-group-class.md)   
 [task_handle 类](task-handle-class.md)