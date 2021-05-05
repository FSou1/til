# How to increase WebSocket performance

There are 2 optional modules that provide a performance boost.

* `npm install --save-optional bufferutil`: efficiently performs operations (masking, unmasking) on the data payload
* `npm install --save-optional utf-8-validate` efficiently check if a message contains valid UTF-8

References:
* https://github.com/websockets/ws#opt-in-for-performance