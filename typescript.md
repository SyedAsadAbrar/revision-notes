# Typescript

### 1. **Type alias** [^1]

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
- In code, this line of code
```
let contactA : string = ContactType.Active;
```
would be replaced by 
```
let contactB : ContactType = "active";
```

### 2. **keyof operator** [^2]

◼️ Defines a **type alias** consisting of **all the properties** on the other type e.g.
```
type ContactFields = keyof Contact;
```
- Variable of `ContactFields` type will only contain properties which exist in `Contact` only, nothing more than that.

[^1]: [TypeScript Essential Training - Combining multiple types with union types](https://www.linkedin.com/learning/typescript-essential-training-14687057/combining-multiple-types-with-union-types?autoplay=true&resume=false&u=2323090)

[^2]: [TypeScript Essential Training - Keyof operator](https://www.linkedin.com/learning/typescript-essential-training-14687057/keyof-operator?autoSkip=true&autoplay=true&resume=false&u=2323090)