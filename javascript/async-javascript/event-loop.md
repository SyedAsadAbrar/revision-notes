# **Javascript**

## **Event Loop**

* How Javascript handles multiple tasks happening at the same time - **Concurrency model**
* Review - [Javascript Runtime](/javascript/behind-the-scenes/javascript-engine-runtime.md#javascript-runtime)
  * **"Container"** which includes all the pieces necessary to execute Javascript Code - **Runtime** (in the Browser)
  * **"Heart"** of the runtime - **Javascript Engine**
    * Where objects are stored in memory - **Heap**
    * Where code is actually executed - **Call Stack**
  * APIs provided to the engine - **Web APIs**
  * Ready-to-be-executed callback functions (coming from events) - **Callback Queue**
  * Sends callbacks from queue to call stack - **Event Loop**