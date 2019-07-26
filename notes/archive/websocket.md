# WebSocket

## Best Practices

* Reconnect in WebSocket.onclose\(\) call back
* Type different Requests and Responses, for example:
  * LoadRequest and LoadResponse

Code:

* [https://github.com/aizatto/crdt-prototype/blob/master/packages/frontend/src/crdt/CRDTWebSocket.ts](https://github.com/aizatto/crdt-prototype/blob/master/packages/frontend/src/crdt/CRDTWebSocket.ts)
* [https://github.com/aizatto/crdt-prototype/blob/master/packages/backend-express/src/server.ts](https://github.com/aizatto/crdt-prototype/blob/master/packages/backend-express/src/server.ts)
* [https://github.com/aizatto/crdt-prototype/blob/master/packages/shared/src/enums.ts](https://github.com/aizatto/crdt-prototype/blob/master/packages/shared/src/enums.ts)

## Random Maybe Useful Links

[https://en.wikipedia.org/wiki/WebSocket](https://en.wikipedia.org/wiki/WebSocket)

[https://developer.mozilla.org/en-US/docs/Web/API/WebSocket](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)

​

[http://davidwalsh.name/websocket](http://davidwalsh.name/websocket)

[http://websocket.org/](http://websocket.org/)

​

[https://medium.com/factory-mind/websocket-node-js-express-step-by-step-using-typescript-725114ad5fe4](https://medium.com/factory-mind/websocket-node-js-express-step-by-step-using-typescript-725114ad5fe4)

[https://github.com/JonnyFox/websocket-node-express](https://github.com/JonnyFox/websocket-node-express)

​

[https://github.com/websockets/ws](https://github.com/websockets/ws)

[https://www.npmjs.com/package/ws](https://www.npmjs.com/package/ws) 13,740,637 dl

[https://www.npmjs.com/package/socket.io](https://www.npmjs.com/package/socket.io) 2,720,400 dl

[https://www.npmjs.com/package/socket.io-client](https://www.npmjs.com/package/socket.io-client) 3,224,869 dl

​

> Note: Socket.IO is not a WebSocket implementation. Although Socket.IO indeed uses WebSocket as a transport when possible, it adds some metadata to each packet: the packet type, the namespace and the ack id when a message acknowledgement is needed. That is why a WebSocket client will not be able to successfully connect to a Socket.IO server, and a Socket.IO client will not be able to connect to a WebSocket server \(like ws://echo.websocket.org\) either. Please see the protocol specification here.

​

[https://npmcompare.com/compare/socket.io,ws](https://npmcompare.com/compare/socket.io,ws)

​

[https://stackoverflow.com/questions/10112178/differences-between-socket-io-and-websockets/38558531\#38558531](https://stackoverflow.com/questions/10112178/differences-between-socket-io-and-websockets/38558531#38558531)

​

[https://www.npmjs.com/package/express-ws](https://www.npmjs.com/package/express-ws)

​

[https://www.educba.com/websocket-vs-socket-io/](https://www.educba.com/websocket-vs-socket-io/)

​

[https://www.npmjs.com/package/peer](https://www.npmjs.com/package/peer) 7,727 dl; depends on ws

[https://www.npmjs.com/package/peerjs](https://www.npmjs.com/package/peerjs) 2,816 dl

​

[https://socket.io/](https://socket.io/)

​



[https://github.com/hapijs/nes](https://github.com/hapijs/nes)

[https://github.com/rse/hapi-plugin-websocket](https://github.com/rse/hapi-plugin-websocket)

[https://patrick-meier.io/realtime-timeline-with-hapi-js-nes-and-rethinkdb/](https://patrick-meier.io/realtime-timeline-with-hapi-js-nes-and-rethinkdb/)

​

[https://github.com/DefinitelyTyped/DefinitelyTyped/blob/master/types/ws/index.d.ts](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/master/types/ws/index.d.ts)

[https://github.com/microsoft/TypeScript/blob/master/lib/lib.dom.d.ts\#L10230](https://github.com/microsoft/TypeScript/blob/master/lib/lib.dom.d.ts#L10230) MessageEvent

​

[https://github.com/y-js/y-websockets-client](https://github.com/y-js/y-websockets-client)

[https://github.com/y-js/y-websockets-server](https://github.com/y-js/y-websockets-server)

[https://github.com/y-js/y-websocket](https://github.com/y-js/y-websocket)



