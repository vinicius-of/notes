![[Pasted image 20240204193822.png]]

- The `context` is used to provide access to a database which is used to load the data for a user by the `id` provided as an argument in the GraphQL query.
- When the database returns, we can construct and return a new `Human` object.
- Note that while resolver function needs to be aware of Promises, GraphQL query does not.
- GraphQL will wait for Promises, Futures, and Tasks to complete before continuing.