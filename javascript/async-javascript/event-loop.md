# **Javascript**

## **Event Loop**

* JavaScript has a runtime model based on an **event loop**, responsible for **executing the code**, **collecting** and **processing events**, and **executing queued sub-tasks** - **Event Loop**
* How Javascript handles multiple tasks happening at the same time - **Concurrency model**
* Review - [Javascript Runtime](/javascript/behind-the-scenes/javascript-engine-runtime.md#javascript-runtime)
  * **"Container"** which includes all the pieces necessary to execute Javascript Code - **Runtime** (in the Browser)
  * **"Heart"** of the runtime - **Javascript Engine**
    * Where objects are stored in memory - **Heap**
    * Where code is actually executed - **Call Stack**
  * APIs provided to the engine - **Web APIs**
  * Ready-to-be-executed callback functions (coming from events) - **Callback Queue**
  * Sends callbacks from queue to call stack - **Event Loop**

### **Async Javascript Behind the Scenes**

* **Synchronous** code is **executed normally** and **pushed** on the call stack as normal
* Whenever we encounter some **async code (with callbacks)**, the **top-level code** (i.e. code not inside the callback) is **executed normally**
* However, the **async tasks** run in the **Web APIs environment** and will **register** the **callback**
* The environment will put the callback into the **callback queue** only when they have **finished** the **async task**
  * For **promises**, there is a separate queue called **microtasks queue** which has **priority** over callback queue
* The **callback queue** contains all the callback functions in an **ordered list** waiting to **get executed**
  * Callback queue also contains **callbacks** coming from **DOM event**s like **clicks** or **key presses** which are **not async**
* **Event loop** looks into the **call stack** and determines whether its **empty or not** (not including the global context)
* If its **empty**, then event loop will take the **first callback** from callback queue and put it onto the **call stack** to be executed, this is called as an **event loop tick**
  * If there are **any queued microtasks** in the microtasks queue, they are **executed before** any **callback** in the callback queue is executed
  * So, microstasks queue may starve callback queue
* Thus, **runtime manages async behaviour** and **JS engine** has **no sense of time**
  * **Event loop** decides which code should be **executed next**
  * **Engine** basically **executes** whatever its given