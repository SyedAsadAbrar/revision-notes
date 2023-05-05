# **React**

## **Context**

* Information is passed in React via **props**
* It can become **inconvenient** and **verbose** if there are **many components in the middle**, or if many components in your app need the **same information**
* The nearest common ancestor could be far removed from the components that need data and **state** needs to be **lifted up high** - **prop drilling**
* **Context** lets the parent component make some information available to any **component in the tree below** it without passing it explicitly through props