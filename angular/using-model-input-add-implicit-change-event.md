# Using a model input add an implicit `change` event

If your component has a model input, it also has an implicit `change` event added to it.

```typescript
import { Component, model } from "@angular/core";

@Component({ selector: "child" })
export class ChildComponent {
  selected = model(false);
}
```

In the parent, you can simply listen to the change of the child component's model change.

```typescript
import { Component } from "@angular/core";

@Component({
  selector: "parent",
  template: ` <child (selectedChange)="handleChange($event)" /> `,
})
export class ParentComponent {
  handleChange(event: boolean) {
    // handle the event
  }
}
```

> A double binding is actually a syntactic sugar for binding + bindingChange event.
