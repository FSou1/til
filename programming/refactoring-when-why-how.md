# Refactoring: When, Why, How

TL;DR. Refactor early, refactor often

## When should you refactor?

You refactor when you've learned something new, when you understand something better than you did before.

It's time to refactor if there is:
* Duplication- violation of the DRY principle
* Outdated knowledge- requirements change, code needs to keep up
* Usage- based on the real users feedback
* Performance bottlenecks

## Why should you refactor?

Time pressure is often used as an excuse for not refactoring. But this is wrong. The longer you wait, the more time investments you'll need. There won't be more time available.

If refactoring is a surgery operation, then you want to remove something that's growing sooner than later. You can go in now, and take it out while it's still small. Wait too long, and you may lose the patient.

> Refactor early, refactor often

## How to refactor?

A few tips from Martin Fowler:
* Don't try to refactor and add functionality at the same time
* Make sure you have good tests before you begin refactoring
* Take short, deliberate steps. If you keep them small, and test after each step, you'll avoid prolonged debugging

![Refactoring](./images/refactor.jfif)

References:
* The Pragmatic Programmer: Your Journey To Mastery, 20th Anniversary Edition (2nd Edition)