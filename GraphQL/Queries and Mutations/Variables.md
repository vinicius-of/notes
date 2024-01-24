- It's not a good pattern to insert dynamic arguments directly into the query string.
- To work with variables, we need to follow three steps:
	- Replace the static value in the query with `$variableName`.
	- Declare `$variableName` as one of the variables accepted by the query.
	- Pass `variableName: value` in the separate, transport-specific such (JSON) variable dictionary.
- ![[Pasted image 20231225233014.png]]
- Now the client-side can simply pass a different variable rather than needing to construct an entirely new query.
- We should never be doing string interpolation to construct queries from user-supplied values.

## Variable Definitions

- To define a variable: `($episode: Episode)`.
- It lists all of the variables, prefixed by $, followed by their type in this case `Episode`.
- All declared variables must be: Scalars, Enums, or Input Object Types.
- Variables definitions can be **optional** or **required**.
- To define as required, you should use `!` next to the `Episode` type.

## Default variables

- Default values can be assigned to the variables in the query.
- Just add the default value after the type declaration.
- ![[Pasted image 20231225235419.png]]