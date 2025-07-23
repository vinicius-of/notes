---
tags:
  - mongodb
  - nosql
aliases:
  - subdocuments
  - subdocument
---

- ``Subdocuments`` são documentos integrados a outros documentos.
- Em Mongoose, isso significa que você pode aninhar ``schemas`` em outros `schemas`.
- Mongoose tem duas noções distintas de subdocuments:
	- Arrays de subdocumentos.
	- Um único subdocumento aninhado.

```javascript
const childSchema = new Schema({ name: 'string' });

const parentSchema = new Schema({
  // Array of subdocuments
  children: [childSchema],
  // Single nested subdocuments
  child: childSchema
});
```

- Note que documentos populados não são subdocumentos em Mongoose. Os dado de um subdocumento são integrados *in a top-level document*.

## O que é um subdocument?

- *Subdocuments* são similares a documentos normais.
- *Schemas* aninhados podem ter [[General/Middlewares|middleware]], uma lógica de validação personalizada, *virtuals* e outras funcionalidades de alto nível para usar.
- A maior diferença é que subdocumentos não são salvos individualmente, eles são salvos quando o documento-pai deles é salvo.

```javascript
const Parent = mongoose.model('Parent', parentSchema);
const parent = new Parent({ children: [{ name: 'Matt' }, { name: 'Sarah' }] });
parent.children[0].name = 'Matthew';

// `parent.children[0].save()` is a no-op, it triggers middleware but
// does **not** actually save the subdocument. You need to save the parent
// doc.
await parent.save();
```

- Subdocumentos tem dois middlewares:
	- ``save()``
	- ``validate()``

## Subdocuments vs. Nested Paths

- Estes são diferentes de forma sutil.

```Javascript
// Subdocument
const subdocumentSchema = new mongoose.Schema({
  child: new mongoose.Schema({ name: String, age: Number })
});
const Subdoc = mongoose.model('Subdoc', subdocumentSchema);

// Nested path
const nestedSchema = new mongoose.Schema({
  child: { name: String, age: Number }
});
const Nested = mongoose.model('Nested', nestedSchema);
```

- Esses dois ``schemas`` parecem similares e os documentos no MongoDB terão a mesma estrutura com ambos os *schemas*, mas eles tem diferenças.
- Primeiro, a instância de `Nested` nunca terá `child === undefined`. Você pode sempre configurar as sub-propriedades de um `child`, mesmo que você não tenha configurado a propriedade `child`.
- Entretanto a instância de `Subdoc` pode ter `child === undefined`.

```javascript
const doc1 = new Subdoc({});
doc1.child === undefined; // true
doc1.child.name = 'test'; // Throws TypeError: cannot read property...

const doc2 = new Nested({});
doc2.child === undefined; // false
console.log(doc2.child); // Prints 'MongooseDocument { undefined }'
doc2.child.name = 'test'; // Works
```