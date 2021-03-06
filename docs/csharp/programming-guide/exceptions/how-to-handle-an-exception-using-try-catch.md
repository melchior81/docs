---
title: "How to handle an exception using try-catch - C# Programming Guide"
ms.date: 07/20/2015
helpviewer_keywords: 
  - "exception handling [C#], try/catch blocks"
  - "exceptions [C#], try/catch blocks"
  - "try/catch blocks [C#]"
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
---
# How to handle an exception using try/catch (C# Programming Guide)
The purpose of a [try-catch](../../language-reference/keywords/try-catch.md) block is to catch and handle an exception generated by working code. Some exceptions can be handled in a `catch` block and the problem solved without the exception being re-thrown; however, more often the only thing that you can do is make sure that the appropriate exception is thrown.  
  
## Example  
 In this example, <xref:System.IndexOutOfRangeException> is not the most appropriate exception: <xref:System.ArgumentOutOfRangeException> makes more sense for the method because the error is caused by the `index` argument passed in by the caller.  
  
 [!code-csharp[csProgGuideExceptions#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#5)]  
  
## Comments  
 The code that causes an exception is enclosed in the `try` block. A `catch` statement is added immediately after to handle `IndexOutOfRangeException`, if it occurs. The `catch` block handles the `IndexOutOfRangeException` and throws the more appropriate `ArgumentOutOfRangeException` exception instead. In order to provide the caller with as much information as possible, consider specifying the original exception as the <xref:System.Exception.InnerException%2A> of the new exception. Because the <xref:System.Exception.InnerException%2A> property is [read-only](../../properties.md#read-only), you must assign it in the constructor of the new exception.  
  
## See also

- [C# Programming Guide](../index.md)
- [Exceptions and Exception Handling](./index.md)
- [Exception Handling](./exception-handling.md)
