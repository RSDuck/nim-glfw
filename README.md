# nim-glfw

A GLFW 3.x interface for Nim.

## examples

Compile and run any of the examples by invoking the `nim` compiler like this from the `examples` directory:
~~~
nim c -r <example>
~~~

This code from `examples/minimal.nim` displays a window for one second and then terminates:
```nim
import os, glfw

proc main =
  glfw.initialize()
  var c = DefaultOpenglWindowConfig
  c.title = "Minimal Nim-GLFW example"
  var w = newWindow(c)
  sleep(1000)
  w.destroy()
  glfw.terminate()

main()
```
All the examples except `minimal.nim` and `events.nim` depend on [nim-glm](https://github.com/stavenko/nim-glm)

## Documentation

Currently no documentation exists, but a symbol list can be generated by invoking these commands from the root directory:
~~~
nim doc2 src/glfw.nim
nim doc2 src/glfw/wrapper.nim
~~~

## Statically linking to GLFW

To link statically with GLFW, define the conditional symbol `glfwStaticLib` (`-d:glfwStaticLib` or `--define:glfwStaticLib`)

## Version history

* 0.2.1
  * fix import errors
  * fix linker errors on windows
  * update nimble metadata
  * update the README example

* 0.2
  * renamed symbols
      TGL_API -> GlApi

      PWin -> Win
      
      geNoErr -> glerrNoError
      
      TGLFW_Err -> GlfwError
      
      TGL_ES_version -> GlEsVersion
      
      and so on
      
  * newWin has been replaced with newGlWin and newGlEsWin
  
## Contributors

[johnnovak](http://github.com/johnnovak): Contributed with ports of the examples.

[def-](http://github.com/def-): Added support for static linking.
