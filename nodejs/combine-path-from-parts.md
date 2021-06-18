# How to combine a path from parts with Node.js

Instead of joining or concatenating strings, you can use the nodejs `path` module and the `join` method:

```javascript
import path from 'path';

function getOutputPath(dest: string, folderName: string, fileName: string): string {
    return path.join(dest, folderName, fileName);
}

getOutputPath('C:\\source', 'git', '.gitignore'); // C:\\source\\git\\.gitignore
```

References:
* https://nodejs.org/api/path.html#path_path_join_paths