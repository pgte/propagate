# propagate

Propagate events from one event emitter into another

## Install

```bash
$ npm install propagate
```

## User

```javascript
  var ee1 = new EventEmitter();
  var ee2 = new EventEmitter();
  propagate(ee1, ee2);

  ee2.on('event', function(a, b) {
    console.log('got propagated event', a, b);
  });

  ee1.emit('event', 'a', 'b');
```

## Unpropagate

You can unpropagate by ending the propagation like this:

```javascript
  var ee1 = new EventEmitter();
  var ee2 = new EventEmitter();
  var p = propagate(ee1, ee2);

  // ...

  p.end();
```
