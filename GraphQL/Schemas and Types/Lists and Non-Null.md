
## Non-Null

- You can apply additional ***type modifiers*** that affect the existing [[Scalar Types]].
- ![[Pasted image 20240126234137.png]]
- Here, we are using a `String` type and marking it as `non-null` by adding an **exclamation mark** ( ! ). This means that our **server always expects** to return a non-null value for this field.
- If the server receives this field as a null value, that will actually **trigger** a GraphQL execution error.
- The `non-null` type modifier can also be used when defining arguments for a field, which will **cause the GraphQL server to return a validation error** if a null value is passed  as that argument.

## Lists

- `List` works in a similar way: We can use a type modifier to mark a type as a `List`, which indicates that this field will return an array of that type.
- To use, wrap the type in square brackets ( [ ] ).
- It works the same for arguments, where **the validation step will expect an array for that value**.
- The `non-null` and `list` modifiers can be **combined**.
- ![[Pasted image 20240126235328.png]]
- This means that the *list itself* can be null, but it can't have any null members.
- ![[Pasted image 20240126235245.png]]
- ![[Pasted image 20240126235415.png]]
- This means that the list itself cannot be null, but it can contain null values.
- ![[Pasted image 20240126235549.png]]