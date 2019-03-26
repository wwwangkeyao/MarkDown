JavaScript 可以用于两种类型的 Selenese 参数：脚本参数和非脚本参数（通常是表达式参数）。很多情况下，你可能需要访问或操作 Selenese 参数中的JavaScript 代码片段中的变量。测试用例中的所有变量被存储在 JavaScript 关联数组中。关联数组用字符串来索引而不是用连续的数字索引。存放测试案例变量的关联数组的变量名是 storedVars。当你想在 JavaScript 代码片段中访问或操作变量时，你需要通过 storedVars['yourVariableName'] 来访问。

# 使用 JavaScript 脚本参数

下面的例子说明了如何使用 JavaScript 代码片段来执行一个简单的数值计算：

| 命令 | 目标 | 值 |
|:----:|:---:|:---:|
|store | Edith Wharton | name|
|storeEval | storedVars[‘name’].toUpperCase() |	uc|
|storeEval | storedVars[‘name’].toLowerCase() |	lc|

# 使用非脚本参数

JavaScript 脚本还可以用于生成参数的值，即使没有指定参数是 script 脚本类型。在这种情况下，通过使用特殊的语法，即整个参数值由 javascript 做前缀，在花括号中放置代码片段，例如：javascript { * 这里是你的代码 * }。下面的例子中在 type 命令的第二个 value 值参数中通过 JavaScript 代码使用这个特殊语法产生参数值：

|命令 | 目标 |值|
|:---:|:---:|:---:|
|store | league of nations | searchString|
|type | q | javascript{storedVars[‘searchString’].toUpperCase()}|