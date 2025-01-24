# JSON stringify inconsistency

| Unsupported types | Passed directly | In an array | In an object |
| ----------------- | --------------- | ----------- | ------------ |
| undefined         | undefined       | 'null'      | omitted      |
| Symbol            | undefined       | 'null'      | omitted      |
| Function          | undefined       | 'null'      | omitted      |
| NaN               | 'null'          | 'null'      | 'null'       |
| Infinity          | 'null'          | 'null'      | 'null'       |
| Regex             | '{}'            | '{}'        | '{}'         |
| Map               | '{}'            | '{}'        | '{}'         |
| Set               | '{}'            | '{}'        | '{}'         |
| WeakMap           | '{}'            | '{}'        | '{}'         |
| WeakSet           | '{}'            | '{}'        | '{}'         |
| BigInt            | TypeError       | TypeError   | TypeError    |
| yclic objects     | TypeError       | TypeError   | TypeError    |
