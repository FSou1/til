# How to fix 'chrome' is not defined (Chrome extension)

If you use eslint on your project, you may get the error like `something` is not defined (e.g. chrome).

In order to fix it, you can define chrome by adding /*global chrome*/ in the top of the file.

```
/*global chrome*/
import React, { Component } from 'react';
```

References:
* https://stackoverflow.com/questions/51411447/using-chrome-api-with-react-js
