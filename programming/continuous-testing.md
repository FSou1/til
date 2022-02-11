# Continuous testing

Don't avoid testing the weak spots.

> Test early, test often, test automatically

Start testing as soon as you have code. A good project may well have more test code that production code. It may be cost effective in the long run.

The test environment should match the production environment closely. Any gaps are where bugs arrise.

## Unit testing

If the parts don't work by themselves, they probably won't work well together.

## Integration testing

With good contracts in place and well tested, any integration issues can be detected easily.

## Validation and verification

As soon as you have an executable UI or prototype, you need to confirm: is what users got actually what they wanted? Does it meet the functional requirements? A bug-free system that answers the wrong question isn't very useful.

## Performance testing

Does it meet non-functional requirements? Is it scalable?

## Testing the tests

Because we can't write perfect software, it follows that we can't write perfect test software either.

**We need to test the tests.**

After you have written a test to detect a particular bug, cause the bug deliberately and make sure the test complans. This ensures that the test will catch the bug if it happens for real.

> Use saboteurs to test your testing

## Testing thoroughly

Once you're done with tests, how do you know if you have tested the code thorougly enough?

You don't. The test coverage tools and 100% test coverage goal won't help either.

A number of tested lines of code is a poor metric. What is important is the number of states that your program may have.

For instance, you've tested this function with `a` and `b` numbers from 0 to 999:

```javascript
int test(int a, int b) {
  return a / (a + b);
}
```

You've tested 1,000,000 states and 999,999 of them will work correctly. But there is still one state that will break it all (both a and b equal to 0).

> Test state coverage, not code coverage

## Property based testing

A great way to explorer how your code handles unexpected states is to have a computer generate those states (test data generation tools).

# Find bugs once

Once a bug is found, it should be the last time it was found. The automated test should be modified to catch it from then on.

> Don't use manual procedures

![Test coverage](./images/test-coverage.jfif)

References:
* The Pragmatic Programmer: Your Journey To Mastery, 20th Anniversary Edition (2nd Edition)