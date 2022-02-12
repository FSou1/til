# How to use path aliases with TypeScript in Node.js

In order to avoid the following problem:

```javascript
import { User } from '../../user/model';
import { Article } from '../../article/model';

import { Cache } from '../../../../cache';
import { MongoDB } from '../../../../mongodb';
```

You can add an alias to the `tsconfig.json` file:

```json
"baseUrl": "./src",
"paths": {
    "@modules/*": ["rest/modules/*"],
    "@services/*": ["services/*"]
}
```

So that the imports now look:

```javascript
import { User } from '@modules/user/model';
import { Article } from '@modules/article/model';

import { Cache } from '@services/cache';
import { MongoDB } from '@services/mongodb';
```

References:
* https://dev.to/larswaechter/path-aliases-with-typescript-in-nodejs-4353