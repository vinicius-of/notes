The example query to provide context from [[GraphQL/Execution/Intro]].
![[Pasted image 20240206002120.png]]

Resolving `appearsIn`.
![[Pasted image 20240206001831.png]]

- The `appeasIn` and `starships` fields can be resolved concurrently.
- Our type system claims `appearsIn` will return a [[Enumeration Types|enums]] values with known values. As you can compare the first image with the second one, it does not return numbers, but strings!
- This is a example of **scalar coercion**. The type system knows what to expect and will convert the values return by a resolver function into something that upholds the API contract.
- In this case, it's using `4, 5, 6` to represent the enum values internally.