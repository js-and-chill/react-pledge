# react-pledge
An higher-order component to constraint rendering

As Relay states it, 95% of components need to answer a specific need : fetch data at mounting, and then display it.  
This HoC is meant to provide a simple way to code it.

* [API](#api)
* [Vanilla Example](#vanilla-example)
* [Redux Example](#redux-example)

### API

* [`createPledge(isResolved(props), resolve(props))`](#api)
  * `isResolved` **props** A function that returns a `boolean`, specifying if the pledge is resolved
  * `resolve` **props** A function that does whatever is needed to try and resolve the pledge when it isn't resolved. The resolve function is only called if the pledge isn't resolve, or if `forceFetch` option is set to `true`.
* [`withPledge(pledge, forceFetch = false)`](#api)
  * `pledge` A pledge object returned by `createPledge`
  * `forceFetch` Wether or not to trigger the resolve function at mounting even if the pledge is already resolved

### Vanilla Example
```js
import React, { Component } from 'react'

