---
tags:
  - back-end
  - mongodb
  - nosql
---
- Instâncias de `Models` são [[Documentos|documentos]]. Documentos tem próprios métodos de instâncias construídos em si. Nós podemos definir nossos próprios métodos de instâncias de documento personalizado.


```javascript
// define a schema
const animalSchema = new Schema({ name: String, type: String },
  {
  // Assign a function to the "methods" object of our animalSchema through schema options.
  // By following this approach, there is no need to create a separate TS type to define the type of the instance functions.
    methods: {
      findSimilarTypes(cb) {
        return mongoose.model('Animal').find({ type: this.type }, cb);
      }
    }
  });

// Or, assign a function to the "methods" object of our animalSchema
animalSchema.methods.findSimilarTypes = function(cb) {
  return mongoose.model('Animal').find({ type: this.type }, cb);
};
```

- Sobrescrever métodos padrões do mongoose pode levar a resultados imprevisíveis.