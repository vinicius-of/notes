![[Pasted image 20240104030038.png]]
- If you are querying a field that returns an interface or an union type, you will need to use ***inline fragments***.
- In this query above, the `hero` field returns the type `Character`, which it may be either a `Human` or `Droid`.
- The result depends on the `episode` argument.
- In the direct selection, you can only ask for fields that exists on the `Character` interface, such as `name`.
- The first fragment is labeled as `... on Droid`, the `primaryFunction` field will only be executed if the `Character` returned from `hero` is of the `Droid` type.
- Similarly for the `height` field for the `Human` type.

## Meta Fields

- Some situations you won't know what type you will get back from the GraphQL service.
- You need some way to determine how to handle that data on the client.
- GraphQL allows you to request `__typename`, a meta field.
- ![[Pasted image 20240124044635.png]]
- In the above query, search returns a union type.
- 