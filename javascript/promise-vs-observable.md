# What is the Difference Between Promises and Observables?

## Promise

* Starts executing immediately once it is defined
* Can return only one value
* Not cancellable by default (need to combine with `AbortController`)
* Promise executes only onces (`promise defined` > `then 1` > `then 2`);

## Observable

* Won't start executing until we subscribe to it
* Can emit multiple streams of values
* Can be canceled by unsubscribing
* Observable executes every time we subscribe (`observable defined` > `subscribe 1` > `observable defined` > `subscribe 2`)

References:
* https://blog.bitsrc.io/promises-vs-observables-674f4bc8ca5e