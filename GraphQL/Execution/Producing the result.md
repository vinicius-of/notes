### Query

```graphql
query() {
	human(id: 1002) {
	    name
	    appearsIn
	    starships {
	      name
	    }
	  }
	}
}
```

### Result

```json
{
  "data": {
    "human": {
      "name": "Han Solo",
      "appearsIn": [
        "NEWHOPE",
        "EMPIRE",
        "JEDI"
      ],
      "starships": [
        {
          "name": "Millenium Falcon"
        },
        {
          "name": "Imperial shuttle"
        }
      ]
    }
  }
}
```

- As each field is resolved, **the resulting value is placed into a key-value map** with the field name (or alias).
- This continues from the bottom leaf fields of the query all the way back up to the original field on the [[Root Fields and Resolvers|root query]].