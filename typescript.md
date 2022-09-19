# Typescript

### 1. **Type alias**

◼️ **Name** given to a type e.g.
```
type PersonName = string;
```
- `type` -> **keyword** to define type
- `PersonName` -> **alias/name** of our new type
- `string` -> "type" of `PersonName` type, in this case a `string`

◼️ Can also be used with **union `|` or ampersand  `&` operator** e.g.
```
type PersonId = string | number;
```
- `PersonId` can be `string` or `number` variable
```
type PersonName = IntA & IntB;
```
- `PersonName` now has **all properties and functions** of `IntA` and `IntB` interfaces.
- This is effectively the same as saying:
```
interface PersonName extends IntA, IntB {}
```
- `extends` -> This is a **keyword** which means that `PersonName` has the **same 'type signature'** as the combination of `IntA` and `IntB`

◼️ Can also replace **enums**
```
enum ContactType {
    "Active" = "active",
    "Inactive" = "inactive"
}
```
becomes
```
type ContactType  = "active" | "inactive";
```
- In code, this block
```
let contactA : string = ContactType.Active;
```
would be replaced by 
```
let contactB : ContactType = "active";
```
