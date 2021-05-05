# How to use WebSocket connections with Node.js

The easiest way to use WebSocket connections is directrly through Node's [ws module](https://github.com/websockets/ws).

Install ([why bufferutil and utf-8-validate matter](/nodejs/increase-ws-performance.md)):
```
npm install --save ws bufferutil utf-8-validate
```

Initialize a server:
```javascript
const wss = new Server({ server });

wss.on('connection', (ws) => {
  console.log('Client connected');
  ws.on('close', () => console.log('Client disconnected'));
});
```

Broadcast updates to clients:
```javascript
setInterval(() => {
  wss.clients.forEach((client) => {
    client.send(new Date().toTimeString());
  });
}, 1000);
```

References:
* https://devcenter.heroku.com/articles/node-websockets