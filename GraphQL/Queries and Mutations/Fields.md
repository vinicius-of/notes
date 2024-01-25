- GraphQL asks for specific fields on object.
- GraphQL queries can traverse related objects and their fields, letting the client fetch lots of related data in one request.
- Fields can have the types to **Objects** and **Strings**.
- Queries can have comments.
- ![[Pasted image 20240125013927.png]]

- You can see immediately that the query has exactly the same shape as the result.
- This is essencial to GraphQL, because you can always get back what you expect.
- We can ask for fields that refers to Objects, you can make a *sub-selection* of fields for that object.
- ![[Pasted image 20240125014749.png]]
- 
  The field `friends` returns an array of items.