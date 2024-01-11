# Haxe Playdate Example

An example project built with the [haxe_pd](https://github.com/assert-justice/haxe_pd) library.

## Installation

Ensure haxe, haxelib, and the playdate sdk are installed.

Run the following to install the haxe_pd library

```
haxelib git haxe_pd git@github.com:assert-justice/haxe_pd.git
```

To build, run

```
haxe build.hxml
```

If they aren't already the `bin/lua` and `dist/Game.pdx` directories will have been created. `bin/lua` contains the intermediate lua code, `dist/Game.pdx` contains the runnable playdate game. Happy coding!

## Notes

The generated lua code contains the following snippet which produces an error when run.

```lua
if package.loaded.luv then
```

As a workaround the file `prelude.lua` is included in the src directory. At compile time the contents of this file are prepended to the `main.lua` file. There might be a better fix for this but this works for now.

Tested for haxe 4.3.3