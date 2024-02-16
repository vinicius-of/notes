![[Pasted image 20240214203125.png]]

- What happens when the `starships` field is resolved?
- It returns a list of Promises to load all the ids to get real Starship objects.
- GraphQL will wait for all of these Promises concurrently before continuing.
- 