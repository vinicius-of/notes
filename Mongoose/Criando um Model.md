Para usar nossa definição de schema, nós precisamos converter o `blogSchema` em um `Model` para trabalhar com. Para isso, nós passamos:

```javascript
const Blog = mongoose.model('Blog', blogSchema);
// ready to go!
```

## Ids

- Por padrão, o Mongoose já adiciona a propriedade `_id` ao seus schemas.

```javascript
const schema = new Schema();
schema.path("_id"); // ObjectId {...}
```

- E quando você cria um novo documento, o Mongoose já adiciona a propriedade ``_id`` do tipo `ObjectId`
- Mongoose também adiciona a propriedade `_id` aos [[Subdocuments|subdocuments]]. Você pode desabilitar a propriedade em seus subdocumentos, o Mongoose permite salvar subdocumentos sem o `_id`.

```javascript
const nestedSchema = new Schema(
  { name: String },
  { _id: false } // <-- disable `_id`
);
const schema = new Schema({
  subdoc: nestedSchema,
  docArray: [nestedSchema]
});
const Test = mongoose.model('Test', schema);

// Neither `subdoc` nor `docArray.0` will have an `_id`
await Test.create({
  subdoc: { name: 'test 1' },
  docArray: [{ name: 'test 2' }]
});
```

- Você pode desabilitar `_id` usando a sintaxe seguinte:

```javascript
const nestedSchema = new Schema({
  _id: false, // <-- disable _id
  name: String
});
```

