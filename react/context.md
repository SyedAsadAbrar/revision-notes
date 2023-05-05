# **React**

## **Context**

* Information is passed in React via **props**
* It can become **inconvenient** and **verbose** if there are **many components in the middle**, or if many components in your app need the **same information**
* The nearest common ancestor could be far removed from the components that need data and **state** needs to be **lifted up high** - **prop drilling**
* **`Context`** lets the parent component make some information available to any **component in the tree below** it without passing it explicitly through props

### **To pass context** [^1]

* Create and export it with `export const MyContext = createContext(defaultValue)`
* Pass it to the `useContext(MyContext)` Hook to read it in any child component, no matter how deep
* Wrap children into `<MyContext.Provider value={...}>` to provide it from a parent

```javascript
// LevelContext.js
import { createContext } from 'react';

export const LevelContext = createContext(1);
```

```javascript
// component in whcih we are going to use it
// Heading.js
export default function Heading({ children }) {
  const level = useContext(LevelContext);
  // ...
}
```

```javascript
// Section.js
import { LevelContext } from './LevelContext.js';

export default function Section({ level, children }) {
  return (
    <section className="section">
      <LevelContext.Provider value={level}>
        {children}
      </LevelContext.Provider>
    </section>
  );
}
```

```javascript
// usage in Section component
<Section level={4}>
  <Heading>Sub-sub-heading</Heading>
  <Heading>Sub-sub-heading</Heading>
  <Heading>Sub-sub-heading</Heading>
</Section>
```

### **Before you use context**

Few alternatives before trying out context:

1. Pass props if there isn't a long chain of prop passing

2. Extract components and pass JSX as children to them 
   1. This reduces the number of layers between the component specifying the data and the one that needs it

### **Usecases**

* Theming
* Routing
* Managing state (alongwith reducers for complex state)

[^1]: [Context Example from React Documentation](https://react.dev/learn/passing-data-deeply-with-context)