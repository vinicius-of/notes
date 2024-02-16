
- It's often useful to ask a GraphQL schema for information about what queries it supports.
- We can use the **introspection system**.
- By querying the `schema` field on the root query, we can obtain the available types from the type system.

## Types

Types available from [starWarsIntrospection-test.ts](https://github.com/graphql/graphql-js/blob/main/src/__tests__/starWarsIntrospection-test.ts)

- **Query, Character, Human, Episode, Droid**: These are the ones that we defined in our type system.
- **String, Boolean**: These are built-in scalars that the type system provided.
- **__Schema, __Type, __TypeKind, __Field, __InputValue, __EnumValue, __Directive**: These all are preceded with a double underscore, indicating that they are part of the introspection system.

## Using introspection system

- Let's take a look at the `Droid` type:

![[Pasted image 20240214205845.png]]

- What if we want to know more about Droid, though?
- For example, is it an interface or an object?

![[Pasted image 20240214205934.png]]

- `kind` returns a `__TypeKind` enum.
- One of whose values is `OBJECT`.

- If we asked about `Character` instead we would find that it is an interface:

![[Pasted image 20240214210059.png]]

- 