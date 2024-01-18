---
tags:
  - missing
  - graphql
---
### Fields

- GraphQL is about asking for specific fields on objects.
- GraphQL queries can traverse related objects and their fields, letting the client fetch lots of related data in one request.
- Fields can have the types to **Objects** and **Strings**.
- Queries can have comments.
  
### Arguments

- You can pass arguments to fields.
- ![[Pasted image 20231014043841.png]]
  
- Every field and nested object can get its own set of arguments, making GraphQL a complete replacement for making multiple API fetches.
- You can even pass arguments into scalar fields to implement data transformations.

  ![[Pasted image 20231014044038.png]]

- Arguments can be of many different types.
- GraphQL comes with a default set of types.
- GraphQL server can also declare its own custom types as long as they can be serialized into your transport format.

### Aliases

- You can make two queries for the same field with different arguments using aliases.
![[Pasted image 20231014044825.png]]

- In the example above, the two `hero` fields would have conflicted.

### Fragments

- Context: Let's say we had a complicated page in our app. We can look at two heroes side by side. We would need to repeat the fields at least once.
- GraphQL includes reusable units called *fragments*.
- Fragments lets you construct sets of fields and them include them in queries.
![[Pasted image 20231218005657.png]]

- The queries could be pretty repetitive if the fields were repeated.
- This concept is used to split complicated app data requirements into smaller chunks.
- Especially when you need to combine lots of UI components.
- Another example:
- ![[Pasted image 20231218012230.png]]
- ![[Pasted image 20231218012354.png]]
- ![[Pasted image 20231218012434.png]]
- 
#### Using variables inside fragments 

- It is possible for fragments to access variables declared in the query or mutation.
- ![[Pasted image 20231218012744.png]]

### Operation name

- The operation type is either: *query*, *mutation*, *subscription*.
- It describes what type of operation you're intending to do.
- The operation type is required.
- You can use the query shorthand syntax, but you can't supply a name or variable definitions for your operation.

- The operation name is a explicit name for your operation.
- Only required in multi-operation documents.
- Use is encouraged because it is very helpful for debugging and server-side logging.

### Variables

- It's not a good pattern to insert dynamic arguments directly into the query string.
- To work with variables, we need to do three things:
	- Replace the static value in the query with `$variableName`
	- Declare `$variableName` as one of the variables accepted by the query.
	- Pass `variableName: value` in the  separate, transport-specific (JSON) variables dictionary.
- ![[Pasted image 20231225233014.png]]
- Now the client-side can simply pass a different variable rather than needing to construct an entirely new query.
- We should never be doing string interpolation to construct queries from user-supplied values.

#### Variable Definitions

- To define a variable: `($episode: Episode)`
- It lists all of the variables, prefixed by $, followed by their type, in this case `Episode`.
- All declared variables must be: Scalars, Enums, or Input Object Types.
- Learn more about it on the [[Schema]] page.
- Variables definitions can be **optional** or **required**.
- To define as required, you should use `!` next to the `Episode` type.

#### Default Variables

- Default vales can be assigned to the variables in the query.
- Just add the default value after the type declaration.
- ![[Pasted image 20231225235419.png]]
