# JSON with comments

You can set a file association between `json` files and `jsonc` language formatting.

In VS Code open Settings in JSON view by using the Command Pallet (`Cmd` + `Shift` + `P`) and enter `Preferences: Open Settings (JSON)`.

Next, add the following:

```json
"files.associations": {
  "*.json": "jsonc"
}
```
