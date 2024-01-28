- We only talked about passing [[Scalar Types]], [[Enumeration Types]] or string, as arguments into a field.
- You can also pass complex objects.
- This is particularly valuable in case of mutations.
- Input types look exactly the same as regular object types, but it uses the keyword `input` instead of `type`.
	- ![[Pasted image 20240128191640.png]]

- A example of using a input object type as argument type.
```graphql
mutation CreateReviewForEpisode
($ep: Episode!, $review: ReviewInput!) 
{
  createReview(episode: $ep, review: $review) {
    stars
    commentary
  }
}
```

- Note: The fields on an input object type can themselves refer to a input object types, but you can't **mix input and output types** in your schema.

- Note 2: Input Object Types also **can't have arguments** on their fields.