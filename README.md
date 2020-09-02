TypeScript config reasonable defaults with type safety focus.

See [annotated version](https://github.com/iuriikomarov/strictts/blob/main/tsconfig.annotated.json).

Start new TypeScript project with `tsconfig.json`:

```
{
    "extends": "strictts",
    "compilerOptions": {
        ...
    },
    ...
}
```

and define project-specific options.

`tsconfig.json` does not define any options from [project](https://www.typescriptlang.org/tsconfig#Basic_Options_6172) and [module resolution](https://www.typescriptlang.org/tsconfig#Module_Resolution_Options_6174) sections since usually they are related mostly to project layout and JS/TS stack legacy.

`tsconfig-project.json` is a recommended place to go if you start pure TS project aimed ES2016 runtimes.

I'm working on the [React.js UI framework](https://ui.poptop.uk.com/latest/) using TypeScript compiler configured with these defaults. The project contains more than 20k lines of code and thrown **zero** runtime exceptions (from ES2016-compliant environments) for more than six months in production.

I do not include `lib.dom` to default compilation to ensure global namespace be pure ES2016 prelude.

I do:

```
import env from "env"
env.console.log(env.document.body)
```

where `env` module is environment-specific module which is `env.d.ts` from TS distro if I run project in a web browser, or `jsdom` bindings if I run project in Node.js test env, and so on. *Explicit definition of environment bindings (or declarations) helps me to deliver solid reliable code which runs in defferent environments without runtime exceptions.*
