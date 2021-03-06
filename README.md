# ufc
Utopia Fantasy Clone

## Game Engine
The game engine will be a Discrete Event Simulator run in functional style. We
will use the State Monad to transfer the state between events and reduce them
over the queue, using Reducers.

links:
  * https://en.wikipedia.org/wiki/Discrete_event_simulation
  * https://en.wikipedia.org/wiki/MapReduce
  * NO  real good link on state monad yet.

## Support older browsers
To support older brwosers we need to include the polyfill for Web Components
You can find the polyfill at:
`https://github.com/webcomponents/webcomponentsjs/blob/master/webcomponents-lite.js`

To support the `import ... from ...` you need to use Webpack and compile two
bundles: vendor.js and app.js, where vendor contains all vendor.s stuff and app.js
contains the minimum-required-app-core files neccessary for the current viewed
page.

In the index.html do:
```
<script type="application/javascript" nomodule defer src="./app.js"></script>
<script type="application/javascript" nomodule defer src="./vendor.js"></script>
```
This will support older web browsers, where modern browsers get the minimum codes
as they are, and older browsers get the WebPack bundles.
