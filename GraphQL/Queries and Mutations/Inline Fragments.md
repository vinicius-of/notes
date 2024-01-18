![[Pasted image 20240104030038.png]]
- If you are querying a field that returns an interface or an union type, you will need to use ***inline fragments***.
- In this query above, the `hero` field returns the type `Character`, which it may be either a `Human` or `Droid`.
- The result depends on the `episode` argument.
- In the direct selection, you can only ask for fields that existe on the `Character` interface, such as `name`.
- The first fragment is labeled as `... on Droid`, the `primaryFunction` field will only be executed if the `Character` returned from `hero` is of the `Droid` type.
- Similarly for the `height` field for the `Human` type.

## Meta Fields