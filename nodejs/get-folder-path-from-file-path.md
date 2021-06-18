# How to extract a folder path from a file path with Node.js

Instead of using `RegExp`, `substring`, and `replace`, you can use the nodejs `path` module and the `dirname` method:

```javascript
import path from 'path';

function getFolderPath(filePath: string): string {
    return path.dirname(filePath);
}

getOutputPath('C:\\source\\git\\.gitignore'); // C:\\source\\git
```

References:
* https://nodejs.org/api/path.html#path_path_dirname_path