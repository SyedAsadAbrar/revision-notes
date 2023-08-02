# **NodeJS**

## **How NodeJS Works**

- Node works in an **asynchronous** (or non-blocking) way
- That is why it is **good** for **I/O intensive** apps
  - Disk or network access
- **Single thread** used to **handle requests**
  - When a request is received, it doesn't wait for the response
  - It moves on to the second request (if any)
  - The response goes to the **event queue**
  - The event queue is monitored and it immediately handles the event if it is free
- **Not** to be **used** for **CPU-intensive apps**
  - Because of **single threaded nature**
  - When one **client** is **interacting**, **others** have to **wait**
  - CPU-intensive processes can be longer so Node is not a good choice
