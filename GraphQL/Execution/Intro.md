- After being validated, a GraphQL query is executed by a GraphQL server which returns a result that mirrors the shape of the request query, typically as JSON.

- GraphQL cannot execute a query without [[Type System|type system]]

- Each field on each type os backed by a function called [[Resolvers|resolvers]] which is provided by the GraphQL server developer.
- When a field is executed, the corresponding *resolver* is called to produce the next value.

- If a field produces a scalar value like a string or number, then the execution completes. However, if a field produces an object value then the query will continue to execute.
- The query will contain another selection of fields which apply to that object.
- This continues until scalar values are reached.
- **GraphQL queries always end at scalar values**.