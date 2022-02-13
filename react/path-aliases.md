# How to use path aliases with TypeScript in Node.js

In order to avoid the following problem:

```javascript
import { IPriceData, IVolumeData } from "../../../models/index";

import { connectToDatabase } from '../../../lib/mongodb';
```

You can add an alias to the `tsconfig.json` file:

```json
"baseUrl": ".",
"paths": {
  "@models/*": ["models/*"],
  "@lib/*": ["lib/*"]
}
```

So that the imports now look:

```javascript
import { IPriceData, IVolumeData } from "@models/index";

import { connectToDatabase } from '@lib/mongodb';
```

References:
* https://dev.to/larswaechter/path-aliases-with-typescript-in-nodejs-4353