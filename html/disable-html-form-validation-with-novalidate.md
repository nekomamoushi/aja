# Disable HTML Form validation with `novalidate`

HTML5 comes with neww input types (email, tel, url, etc) and builtin validation to validate them.

But It can be annoying if you want to test your server-side validation or use a custom validation.

In that case, to disable the native validation, you can use the `novalidate` attribute

You just have to add it tto your form tag.

```html
<form novalidate>
  <label for="phone"></label>
  <input name="phone" type="tel" required />
  <input type="submit" value="submit" />
</form>
```
