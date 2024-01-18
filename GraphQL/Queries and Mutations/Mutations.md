- In REST, any request might end up causing some side-effects on the server, but by convention it's suggested that one does not use `GET` request to modify data.
- GraphQL has established a convention that any operations that cause writes should be sent explicitly via a **mutation**.
- Just like in queries, if the mutation field returns an object type, you can ask for nested fields.
- This can be useful for fetching the new state of an object after an update.
- ![[Pasted image 20231226004956.png]]
- Note how `createReview` fields returns the `stars` and `commentary`.
- This is useful when mutating existing data.
## Multiple fields in mutations

- A mutation can contain multiple fields, just like a query.
- There is a distinction between these two: **While query fields are executed in parallel, mutation fields run in series, one after the other**.
- This means that if we send two `incrementCredits` mutations in one request, the first is guaranteed to finish before the second begins.
- This ensures that we don't end up with a race condition with ourselves.