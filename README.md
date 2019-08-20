# night-lesson

## Why should you have minimum scope for variables?
 1. 对于在程序中不同位置出现同名的变量，通过变量的作用域，我们才能够知道变量对应的值的情况以及使用的时候才知道用的是哪个同名变量的值。
 2. 同时有了变量的最小作用域，能够使代码中不同位置的变量的值都是独立的


## Why should you understand performance of String Concatenation?
 1. 字符串的拼接是程序中最常见的操作之一了，如果使用不当，会引发性能问题。
 2. 最好使用StringBuilder，它的性能要远远好于+操作符与concat（），由于没有保障线程安全的开销，在不需要线程安全的情况下，也优于StringBuffer
 3.  + 操作符会被编译器优化为类似new StringBuilder().append( "" ).append( 200 ).append('B').toString()
，但是可能会由于拼接字符串的操作在循环体内而造成每次循环都会产生创新新的StringBuilder对象，并且StringBuilder默认是创建char[16]的空间，不够再进行扩容，这样会造成大量内存复制的操作开销，以及频繁调用toString带来的开销

## What are the best practices with Exception Handling?
 1. 在Finally块中释放或清理资源，或者使用 try-with-resource, 避免发生异常导致释放资源的代码没有执行
 2. 选择具体的异常抛出，使API更易理解和调用
 3. 自定义的异常可以写Javadoc来说明异常发生的情况
 4. 异常中包含的消息应该是具体说明抛出异常原因
 5. catch异常的顺序应该是越具体的越先被catch
 6. 不要catch Throwable，因为会捕获所有的exception和error，像JVM 产生的OutOfMemoryError 和 StackOverflowError，程序是无法处理的
 7. 不要捕获了异常而什么都不做
 8. 不要又打日志又抛异常
 9. 可以将一般性的异常包装成自定义异常，包装时要使用正确的构造器而不会是异常堆栈信息丢失

## When is it recommended to prefer Unchecked Exceptions?
 如果客服端无法执行任何操作从异常中恢复，如传入的参数中包含 null 值

## When do you use a Marker Interface?
 用于标记或标识特殊操作的空接口

## Why are ENUMS important for Readable Code?
 硬编码只是变量的值，除此之外不会给代码的阅读者额外的信息，而一般通过命名合理的枚举类型，可以知道对应值所属的语义和可取值的范围限制

## Why should you minimize mutability?
 使设计、实现简单，用起来更容易，不容易出错并且更安全

## What is functional programming?
 函数映射关系的编程思想

## Why should you prefer Builder Pattern to build complex objects?
使用简单的对象一步一步地构造复杂的对象，builder类独立于其他的对象；将一个复杂对象的构建与它的表示分离，使得同样的构建过程可以创建不同的表示；
减少构造函数的种类，参数个数，可读性更高，在对象生成过程中，无需复杂逻辑即可生成不可变对象，对象始终以完全状态实例化；

## Why should you avoid floats for Calculations?
 浮点数的运算存在丢失精度的风险

## Why should you build the riskiest high priority features first?
 优先级高且具有较大风险的特性往往意味着该特性的重要程度与影响力都超过了其他特性，该特性能否顺利完成会是此次开发任务成功与否的关键，其他的特性可能会依赖于该特性，该特性也可能是最为重要的功能；由于风险最大，一开始就应该去解决，避免其他的特性完成之后才发现由于存在的风险导致其他特性收到影响，需要修改返工，同时一开始就应该评估相关风险带来的影响，使得开发的进度能够在可控的范围内。所有从重要程度与影响力来说应该首先开发。
