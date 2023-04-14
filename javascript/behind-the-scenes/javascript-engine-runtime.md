# **Javascript**

## **Javascript Engine**

* Program which executes javascript code
  * e.g. V8 Engine for NodeJS and Google Chrome
* Contains a **call stack** and a **heap**
  * Call stack has an execution context where code is executed
  * Heap is an object in memory where objects are stored
![Javascript Engine Diagram](../../javascript/images/js-engine.png)

<details>

<summary>
  Compilation Vs. Interpretation
</summary>

  > **Compilation** - Entire code is converted into machine code at once, and written to a binary file that can be executed by a computer.
  >
  > **Interpretation** - Interpreter runs through the source code and executes it line by line.
  >
  > **Compilation** >>>> **Interpretation** (in terms of speed)

</details>

> **Just-in-time (JIT) compilation** - Entire code is converted into machine code at once, then executed immediately.
>
> Javascript uses this approach.

<details>

<summary>
  JIT Compilation in Javascript
</summary>

1. Code is parsed to form an **AST** (Abstract Syntax Tree)
2. This AST is compiled into machine code
3. The machine code is executed instantly (and is very unoptimized)
4. This unoptimized code is recompiled multiple times to optimize it and replaces the previously used code

![JIT Compilation in Javascript](../../javascript/images/jit-compilation.png)

</details>

## **Javascript Runtime**

* Consists of
  * JS Engine
  * Web APIs
  * Callback Queue
* Event loop acts as intermediary between engine's call stack and callback queue

![Javascript Runtime in Browser](../../javascript/images/js-runtime-browser.png)

![Javascript Runtime in Node](../../javascript/images/js-runtime-node.png)