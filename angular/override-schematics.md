# Overriding Angular Schematics

We can override schematics options for `directives`, `classes`, `services` and many more.

## Schematics

Here is your `angular.json` after you have created your app.

```json
{
  "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
  "version": 1,
  "newProjectRoot": "projects",
  "projects": {
    "demo-app": {
      "projectType": "application",
      "schematics": {},
      "root": "",
      "sourceRoot": "src",
      "prefix": "app",
      "architect": {}
    }
  }
}
```

The option we are interested in here is `schematics`.

Here is the list of available scehmatics:

- `@schematics/angular:component`
- `@schematics/angular:class`
- `@schematics/angular:directive`
- `@schematics/angular:module`
- `@schematics/angular:pipe`
- `@schematics/angular:service`

We will take an example of `@schematics/angular:component` in your project go ahead and below json.

```json
"@schematics/angular:component": {
  "changeDetection": "OnPush",
  "inlineTemplate": true,
  "viewEncapsulation": "None"
}
```

The next step is to run the below command to create a component.

```bash
ng generate component home
```

And notice the difference from the earlier generated component, you will have no html file and `changeDetection` and `viewEncapsulation` properties will be available for you.
