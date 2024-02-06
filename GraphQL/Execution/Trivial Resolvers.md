![[Pasted image 20240206000853.png]]

- Now that a `Human`  object is available. GraphQL execution can continue with the fields requested on it.

- GraphQL knows that the next step is to resolve fields inside of the `Human` type (eg. `name`).
- Resolving the name this case is very straight-forward.
- The `name` resolver function is called and the `obj` argument is the new `Human`.
- In this case, we expect a `Human` object to have a `name` property which we can read and return directly.