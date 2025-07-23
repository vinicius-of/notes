### Documentos vs. Models

- Documentos e [[Models]] são classes distintas no mongoose. A classe `Model` é uma subclasse de uma classe `Document`.
- Quando você constrói um `Model`, você cria um novo `Document`.

- Em mongoose, um `Document` geralmente significa uma instância de um modelo.
- Entretanto, não é aconselhável criar uma instância da classe `Document` sem passar pelo `Model`.

```javascript
const MyModel = mongoose.model('Test', new Schema({ name: String }));
const doc = new MyModel();

doc instanceof MyModel; // true
doc instanceof mongoose.Model; // true
doc instanceof mongoose.Document; // true
```

