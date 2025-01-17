# Binding data attributes

## The problem

```html
<ol class="viewer-nav">
  <li *ngFor="let section of sections" data-sectionvalue="{{ section.value }}">
    {{ section.text }}
  </li>
</ol>
```

However, when you run your Angular application, you encounter the following error message:

```text
EXCEPTION: Template parse errors: Can't bind to 'sectionvalue' since it isn't a known native property.
```

## The solution

The issue here is that Angular treats data attributes differently from regular HTML attributes. To bind a data attribute correctly, you need to use attribute binding instead of the regular interpolation syntax.

To fix the problem, replace `data-sectionvalue="{{ section.value }}"` with `[attr.data-sectionvalue]="section.value"`. Here's the updated code:

```html
<ol class="viewer-nav">
  <li *ngFor="let section of sections" [attr.data-sectionvalue]="section.value">
    {{ section.text }}
  </li>
</ol>
```

By using `[attr.data-sectionvalue]="section.value"`, Angular will recognize the `data-sectionvalue` attribute as a valid binding.
