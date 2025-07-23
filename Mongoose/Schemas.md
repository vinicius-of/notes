---
tags:
  - back-end
  - mongodb
  - nosql
aliases: []
---

## Definindo um `Schema`
- Tudo começa com um ``Schema``. Todo `Schema` mapeia uma coleção no MongoDB e define o formato dos documentos dentro desta coleção.

```javascript
import mongoose from 'mongoose';
const { Schema } = mongoose;

const blogSchema = new Schema({
  title: String, // String is shorthand for {type: String}
  author: String,
  body: String,
  comments: [{ body: String, date: Date }],
  date: { type: Date, default: Date.now },
  hidden: Boolean,
  meta: {
    votes: Number,
    favs: Number
  }
});
```

- Cada chave de `blogSchema` define uma propriedade em nossos documentos que será moldado ao seu [[SchemaType]]. 
- Por exemplo nós definimos a propriedade `title` que será moldado ao tipo `String`.
- Chaves também podem conter objetos aninhados contendo mais definições e chaves como a propriedade `meta`. 
- Em contrapartida, a propriedade `meta` não pode ter uma validação. Para isto, leia o [[Subdocuments]] ou [[Mixed]].
- Os tipos de *schemas* permitidos são:
	-  [String](https://mongoosejs.com/docs/schematypes.html#strings)
	- [Number](https://mongoosejs.com/docs/schematypes.html#numbers)
	- [Date](https://mongoosejs.com/docs/schematypes.html#dates)
	- [Buffer](https://mongoosejs.com/docs/schematypes.html#buffers)
	- [Boolean](https://mongoosejs.com/docs/schematypes.html#booleans)
	- [Mixed](https://mongoosejs.com/docs/schematypes.html#mixed)
	- [ObjectId](https://mongoosejs.com/docs/schematypes.html#objectids)
	- [Array](https://mongoosejs.com/docs/schematypes.html#arrays)
	- [Decimal128](https://mongoosejs.com/docs/api/mongoose.html#mongoose_Mongoose-Decimal128)
	- [Map](https://mongoosejs.com/docs/schematypes.html#maps)
	- [UUID](https://mongoosejs.com/docs/schematypes.html#uuid)
	- [Double](https://mongoosejs.com/docs/schematypes.html#double)
	- [Int32](https://mongoosejs.com/docs/schematypes.html#int32)

- *Schemas* não só definem a estrutura do documento e o molde das propriedades, como também define os métodos de instâncias do documento, o métodos estáticos do ``Model``, indexes compostos e o *hooks* do ciclo de vida do documento chamado [[General/Middlewares|Middleware]].

Próxima página: [[Criando um Model]]