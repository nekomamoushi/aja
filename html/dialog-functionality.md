# Dialog Functionality

|             | `popover`                                    | `<dialog>` modal                              | `<dialog>` non-modal                          | `<div role="dialog">` |
| ----------- | -------------------------------------------- | --------------------------------------------- | --------------------------------------------- | --------------------- |
| Overlay     | yes                                          | yes                                           | yes                                           | yes                   |
| Modal       | no                                           | yes                                           | no                                            | no                    |
| Inert       | no                                           | yes                                           | no                                            | no                    |
| Top Layer   | yes                                          | yes                                           | no                                            | no                    |
| Focus Trap  | no                                           | yes                                           | yes                                           | no                    |
| Dismissible | `echap` or manual                            | `echap`                                       | `echap`                                       | no                    |
| Comments    | Exclusif: open a popover closes the previous | Hidden (default), visible via attribut `open` | Hidden (default), visible via attribut `open` |                       |
