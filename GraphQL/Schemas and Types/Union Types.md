- Union types share similarities with interfaces. However, they lack the ability to define any shared fields among the constituent types.

- ![[Pasted image 20240128183134.png]]
- Wherever we return a `SearchResult` type in our schema, we might get a  `Human`, a `Droid` or a `Starship`.
- Note that members of a union type need to be concrete object types.
- If you query a field that returns the `SearchResult` union type, you need to use a [[Inline Fragments]] to be able to query any fields at all:
	- ![[Pasted image 20240128184032.png]]

- The [[Inline Fragments#^d8d8ad|typename]] meta field resolves to a `String` which lets you differentiate different data types from each other on the client.

- Also, using prior case, since `Human` and `Droid` share a common interface (`Character`), you can query their common fields in one place rather than having to repeat the same fields across multiple types:
	- ![[Pasted image 20240128191237.png]]

- Note: `Starship` is not a `Character`, so it should specify the `name` field.