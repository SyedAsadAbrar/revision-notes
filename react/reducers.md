# **React**

## **Reducers**

* Components with many state updates spread across many event handlers can get overwhelming
* **Consolidating state update logic** outside your component in a **single function** - **`Reducer`**
* **Redux** uses this approach
* Example of **declarative programming**
  * They tell **how** the **state should change** in response to an action
  * **Does not specify** exact **sequence of operations** or **control flow**
  * It takes previous state and an action, returns new state based ona ction type and payload
* Reducers are **pure functions**

### **Move from setting state to dispatching actions**\

1. Replace `setState` 
   
```javascript
function handleAddTask(text) {
    // the object passed to dispatch 
    // function is 'action' object
    dispatch({
        type: 'added',
        id: nextId++,
        text: text,
    });
}

function handleChangeTask(task) {
    dispatch({
        type: 'changed',
        task: task,
    });
}

function handleDeleteTask(taskId) {
    dispatch({
        type: 'deleted',
        id: taskId,
    });
}
```