- A interface is an **abstract** type that includes a certain set of fields that a type must include to implement the interface.
- It's different from **Type**, it could not be implemented directly to a query because it's not a concrete type.

- For example, you could have an interface `Character` that represents any character in the Star Wars trilogy:
- ![[Pasted image 20240128181934.png]]
- This means that any type that *implements* `Character` needs to have these exact fields.

- Implementation examples of `Character` on types:
	- ![[Pasted image 20240128182117.png]]
- You see that both of these types have all of the fields from the `Character` interface.
- It also brings extra fields such as: `totalCredits`, `starships`, `primaryFunction`, that are specific to that particular type.
- To access a type that implements `Character`, you should use [[Inline Fragments]], from that you can use any concrete from both `Character` and `Human` or `Droid`.
- ![[Pasted image 20240128182944.png]]

- Interface are useful when you want to return an object or set of objects.