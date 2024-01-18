---
tags:
  - query-mutations
aliases: []
---

- Context: Let's say that we had a complicated page in our app. We can look at two heroes side by side. We would need to repeat the fields at least once.
- GraphQL includes reusable unis called *fragments*.
- Fragments lets you construct sets of fields and include them in queries.
- ![[Pasted image 20231218005657.png]]
- The queries could be pretty repetitive if the fields were repeated.
- This concept is used to split complicated app data requirements into smaller chunks.
- Especially when you need to combine lots of UI components.
- Another example:
- ![[Pasted image 20231218012230.png]]
- ![[Pasted image 20231218012354.png]]
- ![[Pasted image 20231218012434.png]]

## Using variables inside fragments

- It is possible for fragments to access variables declared in the query or mutation.
- ![[Pasted image 20231218012744.png]]