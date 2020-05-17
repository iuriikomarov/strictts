TypeScript config reasonable defaults with type safety focus.

See [annotated version](https://github.com/iuriikomarov/strictts/blob/main/tsconfig.annotated.json).

Start new TypeScript project with `tsconfig`:

```
{
    "extends": "strictts",
    "compilerOptions": {
        ...
    }
```

and define project specific options.

Blueprint do not define any options from [project](https://www.typescriptlang.org/tsconfig#Basic_Options_6172) and [module resolution](https://www.typescriptlang.org/tsconfig#Module_Resolution_Options_6174) sections.

Soon:

- tslint/eslint blueprint configs
- project templates for different stacks
