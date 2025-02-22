---
title: Scope（作用域）
slug: Glossary/Scope
---
当前的执行上下文。{{glossary("value","值")}}和**表达式**在其中 "可见" 或可被访问到的上下文。如果一个**{{glossary("variable","变量")}}**或者其他表达式不 "在当前的作用域中"，那么它就是不可用的。作用域也可以根据代码层次分层，以便子作用域可以访问父作用域，通常是指沿着链式的作用域链查找，而不能从父作用域引用子作用域中的变量和引用。

当然，一个 {{glossary("function","Function")}} 将生成一个闭包（通常是返回一个函数引用），这个函数引用从外部作用域（在当前环境下）可以访问闭包内部的作用域。例如，下面的代码是无效的，并不是闭包的形式）：

```js
function exampleFunction() {
    var x = "declared inside function";  // x 只能在 exampleFunction 函数中使用
    console.log("Inside function");
    console.log(x);
}

console.log(x);  // 引发 error
```

但是，由于变量在函数外被声明为全局变量，因此下面的代码是有效的（当前作用域不存在的变量和引用，就沿着作用域链继续寻找）：

```js
var x = "declared outside function";

exampleFunction();

function exampleFunction() {
    console.log("Inside function");
    console.log(x);
}

console.log("Outside function");
console.log(x);
```

英文原文中，只提到了闭包的简单特例，也就是父作用域引用子作用域的变量或者引用。这儿做一个补充，当一个函数（foo）执行返回一个内部函数（bar）引用时，bar 将会保存 foo 的作用域引用。例如：

```js
function foo() {
    const str = "bar in foo";
    return function bar() {
        return str;
    }
}

var fun = foo();
fun(); // "bar in foo"
```

## 了解更多

### 基础知识

- Wikipedia 上的 [Scope (computer science)](https://zh.wikipedia.org/wiki/Scope_(computer_science))
