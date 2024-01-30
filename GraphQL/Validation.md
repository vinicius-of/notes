- By using the [[Type System|type system]], it can be predetermined whether a GraphQL query is valid or not.
- This allows servers and clientes to inform developers when an invalid query has been created, without relying on runtime checks.

## Valid Query

- To start, let's take a complex valid query.

![[Pasted image 20240129212413.png]]

- This is a nested query with fragments.
- It's a valid query.
### Example 1

- Let's take a look at some invalid queries: 

![[Pasted image 20240129212605.png]]

- A fragment cannot refer to itself or create a cycle, as it could result in an unbounded result.
- `"message": "Cannot spread fragment \"NameAndAppearancesAndFriends\" within itself."`,

### Example 2

![[Pasted image 20240129213940.png]]

- `message: "Cannot query field \"favoriteSpaceship\" on type \"Character\"."`
- When we query for fields, we have to query for a field that exists on the given **type**.
- So as `hero` returns a `Character`, we have to query for a field on `Character`.
- The type `Character` does not have a `favoriteSpaceship` field, so this query is invalid.

### Example 3

![[Pasted image 20240129220800.png]]

- `"message": "Field \"hero\" of type \"Character\" must have a selection of subfields. Did you mean \"hero { ... }\"?",`
- Whenever we query for a field and it return something other than a scalar or an enum, it's necessary to specify what data we want to get back from the field.
- `hero` returns a `Character`, and it has been requesting fields like `name` and `appearsIn` on it.
- If we omit that, the query will not be valid.

### Example 4

![[Pasted image 20240129221343.png]]
`# INVALID: name is a scalar, so fields are not permitted`

- Still in the context from prior example, if a field is a scalar, it does not make sense to query for additional fields on it. It will result in a invalid query.

### Example 5

![[Pasted image 20240129221821.png]]
`# INVALID: primaryFunction does not exist on Character`

- `"message": "Cannot query field \"primaryFunction\" on type \"Character\". Did you mean to use an inline fragment on \"Droid\"?",`
- That query is invalid because `primaryFunction` is not a field on `Character`.
- We can use [[Fragments]] (verbose but reusable) or [[Inline Fragments]] to do this.
- ![[Pasted image 20240129222741.png]]
- ![[Pasted image 20240129222727.png]]
- By setting up a fragment defined on `Droid` and including it, we ensure that we only query for `primaryFunctions` where it is defined.