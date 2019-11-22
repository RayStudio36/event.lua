# event.lua

A tiny event module for Lua.

## Installation

The [event.lua](https://github.com/RayStudio36/event.lua/blob/master/event.lua) file should be dropped into an existing project and required by it.

```lua
Event = require 'event'
```

## Example

```lua
Event = require 'event'

e = Event()

e:on('test', function(msg) print(msg) end)

e:dispatch('test', 'hello event')
-- print 'hello event'
```

Event with table instance

```lua
t = {}
function t:onTest(msg)
    print('t onTest' .. msg)
nd

e:on('test_t', t.onTest, t)

e:dispatch('test_t', 'hello event')
-- print 't onTesthello event'
```

## Usage

### event:on(name, callback, instance)

Handle events of type `name` with `callback`, `instance` is an optional argument

### event:remove(name, callback)

Remove `callback`

### event:dispatch(name, ...)

Dispatch an event of type `name` with optional arguments

### event:clear(name)

Clear callbacks of type `name`, if `name` is nil, clear all callbacks
