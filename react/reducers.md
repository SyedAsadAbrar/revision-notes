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
* Each action describes a **single user interaction**, even if that leads to **multiple changes in the data**

### **Move from setting state to dispatching actions**\

1. Replace `setState` with `dispatch` functions

```javascript
// example of `setState`

// function handleAddTask(text) {
//     setTasks([
//         ...tasks,
//         {
//         id: nextId++,
//         text: text,
//         done: false,
//         },
//     ]);
// }

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

2. Write a **reducer** function

   * A reducer function is where you will put your **state logic**
   * It takes **two arguments**, the **current state** and the **action object**, and it returns the **next state**

```javascript
function tasksReducer(tasks, action) {
    switch (action.type) {
        case 'added': {
        return [
            ...tasks,
            {
            id: action.id,
            text: action.text,
            done: false,
            },
        ];
        }
        case 'changed': {
        return tasks.map((t) => {
            if (t.id === action.task.id) {
            return action.task;
            } else {
            return t;
            }
        });
        }
        case 'deleted': {
        return tasks.filter((t) => t.id !== action.id);
        }
        default: {
        throw Error('Unknown action: ' + action.type);
        }
    }
}
```

3. Use reducer from your function

```javascript
import { useReducer } from 'react';

// old way using `setState`
// const [tasks, setTasks] = useState(initialTasks);

const [tasks, dispatch] = useReducer(tasksReducer, initialTasks);

// dispatch function returned from useReducer is used in dispatch functions

// dispatch functions are defined here
```