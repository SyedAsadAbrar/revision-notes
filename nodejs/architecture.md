# **NodeJS**

## **Architecture**

- There are **different** kinds of **runtime environments** for running Javascript code in different browsers
  - **Runtime environments** basically provide the **specific modules** or pieces of code needed to **run a piece of code**
  - Each browser provides their own runtime environments
  - This is why **Javascript** code may **behave differently** on **different browsers**
- **Each browser** has a **Javascript engine** which is used to execute our Javscript code
  - `v8` for **Chrome**, `SpiderMonkey` for **Firefox** and `Chakra` for **Internet Explorer**
- **Node** is a **runtime environment** which uses the **v8 engine** (inside C++ code) to run **Javascript code outside of browser**
  - It also includes **other objects** needed **to run Javascript code** such as `fs` or `http` modules forming the **runtime environment**
