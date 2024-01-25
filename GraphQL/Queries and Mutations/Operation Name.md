- ![[Pasted image 20240125020354.png]]
- The operation type is either:  `query`, `mutation`, `subscription`.
- It describes which type of operation you are intending to execute.
- The operation type is always **required** unless you are using `query` shorthand syntax as such:
```
	{
		hero {
			name
			friends {
				name
			}
		}
	}
```
- The operation name is a meaningful and explicit name for your operation.
- Its use is encouraged because it is very helpful for debugging and server-side logging.
