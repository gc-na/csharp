<!--
Meta Description: # C#中的finally关键字详解 ## 摘要 在C#中，`finally`关键字用于确保一段代码在异常处理后始终执行，无论是否发生异常。这对于释放资源和清理操作非常重要。 ## 文档 `finally`块是与`try`和`catch`语句一起使用的，目的是确保某些代码在异常处理后总是执行。即使在...
Meta Keywords: finally, try, filestream, catch, null
-->

# C#中的finally关键字详解

## 摘要
在C#中，`finally`关键字用于确保一段代码在异常处理后始终执行，无论是否发生异常。这对于释放资源和清理操作非常重要。

## 文档
`finally`块是与`try`和`catch`语句一起使用的，目的是确保某些代码在异常处理后总是执行。即使在`try`块中发生了未处理的异常，`finally`块中的代码仍然会被执行。通常用于释放资源，如关闭文件、网络连接或数据库连接等。

### 用法
`finally`块的基本结构如下：

```csharp
try
{
    // 可能会引发异常的代码
}
catch (Exception ex)
{
    // 处理异常的代码
}
finally
{
    // 无论是否发生异常，始终执行的代码
}
```

在`finally`块内的代码通常用于清理操作，例如：

- 关闭文件
- 释放资源
- 释放数据库连接

## 示例
以下是一个简单的使用`finally`的示例：

```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        FileStream fileStream = null;
        try
        {
            fileStream = new FileStream("example.txt", FileMode.Open);
            // 读取文件内容
        }
        catch (FileNotFoundException ex)
        {
            Console.WriteLine("文件未找到: " + ex.Message);
        }
        finally
        {
            if (fileStream != null)
            {
                fileStream.Close();
                Console.WriteLine("文件流已关闭.");
            }
        }
    }
}
```

在上面的示例中，即使在读取文件时发生异常，`finally`块也会确保文件流被关闭。

## 说明
使用`finally`时需要注意以下几点：

1. **确保资源释放**：在使用`finally`块时，确保所有需要释放的资源都在其中处理。
2. **避免不必要的代码**：`finally`块不应包含可能导致异常的代码，因为这可能会隐藏原始异常。
3. **与`try`块结合**：`finally`块必须与`try`或`catch`块一起使用，不能单独使用。

### 常见错误
- 忘记在`finally`块中检查对象是否为`null`，可能导致`NullReferenceException`。
- 在`finally`块中抛出异常会覆盖`try`或`catch`中的异常，可能导致调试困难。

## 一句话总结
`finally`关键字用于确保在异常处理后始终执行特定代码块，适合用于资源清理和释放。