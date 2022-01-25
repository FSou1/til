# How to unit test Next.js with Jest

- Install the packages with `npm install jest babel-jest @types/jest --save-dev`
- Add a test script to the `package.json`:

```json
{
  // ...
  "scripts": {
    // ...
    "test": "jest"
  }
}
```

- Create the `.babelrc` file:

```json
{
  "presets": ["next/babel"]
}
```

- Add a test:

```typescript
# tests/lib/locations.test.ts

import {
  getCountries,
  ILocation,
  ILocationResponseItem
} from "../../lib/locations";

describe('Check we parse locations response', () => {
  test('getCountries transforms country objects to locations array', () => {
    const locations = [
      {
        "_id": "61ee3b8215419247a6f0ba42",
        "region": "Americas",
        "region_id": "4060741400044103994",
        "country": "USA",
        "location_id": "4000602900000005338",
        "states": {},
        "cities": []
      },
      {
        "_id": "61ee3b8215419247a6f0ba44",
        "region": "WE",
        "region_id": "4060741400044109082",
        "country": "UK",
        "location_id": "4000602900000005341",
        "states": {},
        "cities": []
      }
    ];
    const expected: ILocation[] = [
      {
        location_id: '4000602900000005338',
        location_name: 'USA'
      },
      {
        location_id: '4000602900000005341',
        location_name: 'UK'
      }
    ];
    const actual = getCountries(locations);
    expect(actual).toEqual(expected);
  });
});
```

- Run the test with `npm run test`:

```
C:\Projects\git\opp\ui>npm run test

> test
> jest

 PASS  tests/lib/locations.test.ts
  Check we parse locations response
    √ getCities transforms cities array to locations array (1 ms)
    √ getCountries transforms country objects to locations array

Test Suites: 1 passed, 1 total
Tests:       2 passed, 2 total
Snapshots:   0 total
Time:        0.331 s
Ran all test suites.
```

References:
* https://www.youtube.com/watch?v=lNdcdtSdCEQ