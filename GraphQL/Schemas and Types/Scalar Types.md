- A GraphQL object types has a name and fields, but some point those fields have to resolve to some concrete data.
- That's where the scalar types come in: they represent the leaves of the query.
- ![[Pasted image 20240126232415.png]]
- `name` and `appearsIn` fields will resolve to scalar types.
- GraphQL comes with a set of default scalar types out of the box.
	- `Int`: A signed 32-bit.
	- `Float`: A signed double-precision floating-point value.
	- `String`: A UTF-8 character sequence.
	- `Boolean`: `true` or `false`
	- `ID`: The ID scalar type represents a unique identifier, often used to refetch an object or as the key for a cache. The ID type is serialized in the same way as a String. Defining it as an ID means that it is not intended to be human-readable.

- There is also a way to specify custom scalar types.
	- `scalar Date`

- It's up to our implementation to define how that type should be serialized, deserialized, and validated.