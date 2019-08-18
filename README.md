# night-lesson

## Why should you have minimum scope for variables?
 1. 对于在程序中不同位置出现同名的变量，通过变量的作用域，我们才能够知道变量对应的值的情况以及使用的时候才知道用的是哪个同名变量的值。
 2. 同时有了变量的最小作用域，能够使代码中不同位置的变量的值都是独立的


## Why should you understand performance of String Concatenation?
 1. 字符串的拼接是程序中最常见的操作之一了，如果使用不当，会引发性能问题。
 2. 最好使用StringBuilder，它的性能要远远好于+操作符与concat（），由于没有保障线程安全的开销，在不需要线程安全的情况下，也优于StringBuffer
 3. 使用+会new 很多对象

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
 使用函数开发软件的编程模式

## Why should you prefer Builder Pattern to build complex objects?

## Why should you avoid floats for Calculations?
 会丢失精度

## Why should you build the riskiest high priority features first?
 高优先级
