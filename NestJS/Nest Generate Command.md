Generates and/or modifies files based on a schematic

```bash
nest generate <schematic> <name> [options]
nest g <schematic> <name> [options]
```

### Arguments

- `<schematics>`: The schematic to generate.
- ``<name>``: The name of the generated component.

### Schematics

- `app`: Generate a new application within a monorepo.
- `library`: Generate a new library within a monorepo.
- `class`: Create a new class
- `controller`
- ``decorator``
- `filter`
- `gateway`
- `guard`
- `resource`: Generate a new [[CRUD resource]].
- `interface`
- `module`
- `middleware`
- `pipe`
- `provider`
- `resolver`
- `service`