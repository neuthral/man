#  屋 ya - simple glob pub/sub store

## Simple to use

### simple event listening and emitting
```javascript
const ya = require( 'ya' )
const store = ya()

store.on( 'foo', function ( data ) {
  console.log( data )
} )

store.emit( 'foo', 'bar' )
```
> bar

### glob ( minimatch ) event listening
```javascript
store.glob( '/users/*', function ( evts ) {
  evts.forEach( function ( evt ) {
    console.log( evt.evt + ' ' + evt.data )
  } )
} )

store.emit( 'foo', 'bar' ) // not matched by above glob
store.emit( '/users/123', '123' )
store.emit( '/users/456', '456' )
```
console
```bash
/users/123 123
/users/456 456
```

# About
Simple glob ( minimatch ) event emitting and listening.

# Why
A nuggest above simple mutable `{}` state management and barebones EventEmitting, but nothing sophisticated like MobX or Redux.

Diffing, mutation and notification is all up to the user/programmer.

# For who?
For people or projects that don't need a sophisticated store and can manage with the barebones.

This helps you maintain your ad-hoc mutable vanillajs `{}` state.

Good for tiny projects and prototyping where there is no point in configuring and maintaining a sophisticated store ( yet ).

# How
[minimatch](https://github.com/isaacs/minimatch)

# Alternatives
[glob-events](https://www.npmjs.com/package/glob-events)

# Test
```bash
npm test
```
