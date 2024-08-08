- Javascript provides primitives like `string` and `number`, but it does not check that you've consistently assigned these. Typescript does.

## Types by Inference

- Typescript will generate types for the programmer in many cases.

- For example in creating a variable and assigning it to a particular value, Typescript will use the value as its type.

```typescript
let helloWorld = "Hello World"
// let helloWorld: string
```

## Defining Types

- For example, to create an object with an inferred type which includes `name: string` and `id: number`, you can write:

```typescript
const user = {
	name: "Hayes",
	id: 0
}
```

- You can explicitly describe this object's shape using an `interface` declaration:

```typescript
interface User {
	name: string,
	id: number
}
```

- You can then declare that a Javascript Object conforms to the shape of your new `interface` by using syntax like `: TypeName` after a variable declaration.

```typescript
const user: User = {
	name: "Hayes",
	id: 0
}
```

- If you provide an object that does not match the interface you have provided, Typescript will warn you.
- Typescript does support classes and object-oriented programming.

- You can use interfaces to annotate parameters and return values to functions:

```typescript
function deleteUser(user: User) {}

function getAdminUser(): User {}
```

- Typescript extends the list of types supported by Javascript with a few more, such as:
	- `any`: Allow anything.
	- `unknown`: Ensures that someone declares what the type is.
	- `never`: It's not possible that this type could happen.
	- `void`: a function which returns `undefined` or has no return value.

## Composing Types

- With Typescript, you can create complex types by combining simple ones. There are two popular ways to do so:

### Unions

- With Unions, you can declare that a type could be one of many types:

```typescript
type MyBool = true | false;
```

### Generics

- **Generics** provide variables to types.
- An array with generics can describe the values that the array contains.
- You can declare your own types that use generics:

```typescript

interface Backpack<Type> {
	add: (obj: Type) => void,
	get: () => Type
}

declare const backpack: Backpack<string>;

// The backpack will return a string, as declared before.
const object = backpack.get();
```

## Structural Type System

- One of Typescript's core principles is that type checking focuses on the *shape* that values have.
- This is sometimes called "duck typing" or "structural typing".

- There is no difference between how classes and objects conform to shapes.
- If the object, instance or class has all required properties, Typescript will say they match, regardless of the implementation details.