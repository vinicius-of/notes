	SWC is an extansible Rust-based platform that can be used for both compilation and bundling.

### Installation

To install, use: `npm i --save-dev @swc/cli @src/core`

To use swc builder, use: `nest start -b swc`

``nest-cli.sjon``

```json
{
  "compilerOptions": {
    "builder": "swc"
  }
}
```

### Type checking

SWC does not perform any type checking itself. To activate, use `--type-check` flag.

### SWC Configuration

You can customize the configuration by creating a `.swcrc` file in the root directory and tweaking the options as you wish.

```json
{
  "$schema": "https://swc.rs/schema.json",
  "sourceMaps": true,
  "jsc": {
    "parser": {
      "syntax": "typescript",
      "decorators": true,
      "dynamicImport": true
    },
    "baseUrl": "./"
  },
  "minify": false
}
```

### Common pitfalls

If you use TypeORM or any other ORM in your application, you may stumble upon circular import issues.

SWC does not handle circular imports well. You should use the following workaround:


```javascript
@Entity()
export class User {
  @OneToOne(() => Profile, (profile) => profile.user)
  profile: Relation<Profile>; // <--- see "Relation<>" type here instead of just "Profile"
}
```

	Hint: `Relation` type is exported from the `typeorm` package.