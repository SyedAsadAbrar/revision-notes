# **React**

## **Redux**

* Flow:
  * UI dispatches **action**
  * **Reducer** gets action, runs some operation on it and updates state
  * Store updates UI after change in state
* Multiple reducers are possible with `combineReducers` function
* Multiple stores are possible but not recommended
* Reducer must be pure function
  * Redux does shallow-comparison to check whether state has updated or it will not re-render
    * Hence, we cannot mutate state but must always return a new state object
  * We should be able to call them multiple times with same effect so it becomes **predictable** 
    * Testing becomes easier
    * Replay behaviour using Redux DevTools will get affected