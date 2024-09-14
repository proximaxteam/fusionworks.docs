# 代码执行

## 目录

* [介绍](code.md#jie-shao)
* [使用场景](code.md#shi-yong-chang-jing)
* [限制](code.md#xian-zhi)

## 介绍

代码节点支持运行 Python / NodeJS 代码以在工作流程中执行数据转换。它可以简化您的工作流程，适用于Arithmetic、JSON transform、文本处理等情景。

该节点极大地增强了开发人员的灵活性，使他们能够在工作流程中嵌入自定义的 Python 或 Javascript 脚本，并以预设节点无法达到的方式操作变量。通过配置选项，你可以指明所需的输入和输出变量，并撰写相应的执行代码：

<figure><img src="../../../.gitbook/assets/image (157).png" alt="" width="375"><figcaption></figcaption></figure>

## 配置

如果您需要在代码节点中使用其他节点的变量，您需要在`输入变量`中定义变量名，并引用这些变量，可以参考[变量引用](../key\_concept.md#变量)。

## 使用场景

使用代码节点，您可以完成以下常见的操作：

### 结构化数据处理

在工作流中，经常要面对非结构化的数据处理，如JSON字符串的解析、提取、转换等。最典型的例子就是HTTP节点的数据处理，在常见的API返回结构中，数据可能会被嵌套在多层JSON对象中，而我们需要提取其中的某些字段。代码节点可以帮助您完成这些操作，下面是一个简单的例子，它从HTTP节点返回的JSON字符串中提取了`data.name`字段：

```python
def main(http_response: str) -> str:
    import json
    data = json.loads(http_response)
    return {
        # 注意在输出变量中声明result
        'result': data['data']['name'] 
    }
```

### 数学计算

当工作流中需要进行一些复杂的数学计算时，也可以使用代码节点。例如，计算一个复杂的数学公式，或者对数据进行一些统计分析。下面是一个简单的例子，它计算了一个数组的平方差：

```python
def main(x: list) -> float:
    return {
        # 注意在输出变量中声明result
        'result' : sum([(i - sum(x) / len(x)) ** 2 for i in x]) / len(x)
    }
```

### 拼接数据

有时，也许您需要拼接多个数据源，如多个知识检索、数据搜索、API调用等，代码节点可以帮助您将这些数据源整合在一起。下面是一个简单的例子，它将两个知识库的数据合并在一起：

```python
def main(knowledge1: list, knowledge2: list) -> list:
    return {
        # 注意在输出变量中声明result
        'result': knowledge1 + knowledge2
    }
```

## 限制

无论是Python还是Javascript，它们的执行环境都被严格隔离（沙箱化），以确保安全性。这意味着开发者不能使用那些消耗大量系统资源或可能引发安全问题的功能，如直接访问文件系统、进行网络请求或执行操作系统级别的命令。这些限制保证了代码的安全执行，同时避免了对系统资源的过度消耗。
