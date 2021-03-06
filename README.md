# [Wonderland][wonderland]

Wonderland is a simple tweening library for Lua.

[Hump.timer][hump] is as simple as a tweening library can get, while [Flux][flux] and [Tween][tween] are too abstracted away, modifying multiple properties inside a table .

Neither [Hump][hump] nor [Tween][tween] offer a simple way to chain tweens like [Flux][flux] does with `tween:after()`.

Wonderland is the middle ground that tries to address some of this problems.

> You should still check the other libs, deciding between them depends on taste and specific use case

## Usage

> Animate doesn't have any dependencies, but it should be noted that it doesn't implement or include any kind of internal clock, so you either need a module to do that or your framework should be able to give you time deltas.

So to use the library, drop `wonderland.lua` somewhere and require it
```lua
local wonderland = require 'wonderland'
```

You can then create a new `animation`, and start adding keyframes
```lua
local animation = wonderland.new(10) -- Initial value 10
  :add{'delay', length = 10}
  :add{'linear', length = 4, value = 12}
  :add{'cubic-inout', length = 3, value = 10}
```

Generally you want to create a `playback` object from your `animation`
```lua
local playback = animation:newPlayback()
```

Then in your main loop you would call `playback:update(dt)` to get the new value of the animation.

Check the [wiki][wiki] for information on what each function does.

## License

Wonderland is licensed under the terms of the [MIT License][mit].

Copyright (c) 2017 Pablo A. Mayobre ([Positive07][positive])

[wonderland]: https://github.com/Positive07/wonderland.lua
[hump]: hump.readthedocs.io/en/latest/timer.html
[tween]: https://github.com/kikito/tween.lua
[flux]: https://github.com/rxi/flux
[wiki]: https://github.com/Positive07/wonderland.lua/wiki
[mit]: https://github.com/Positive07/wonderland.lua/blob/master/LICENSE
[positive]: https://github.com/Positive07
