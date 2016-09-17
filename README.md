# wahsp

### Overview
*wahsp* (Web Audio HaSkell Protocol) is a binding for Haskell to the
[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) ala *blank-canvas@*
Audio sources, effects, etc. can be combined, manipulated, and otherwise controlled using haskell
and are then rendered in the the browser (see the above link for browser compatibility).

### Installation

As of the writing of this README, remote-monad 0.3 is only available on github and must be built
from the repo.

#### Full installation instructions:

```
cabal install natural-transformation
git clone https://github.com/ku-fpg/remote-monad.git
cd remote-monad/
cabal install
cd ../
cabal install
```

### Example

Here is a basic program that creates a 200Hz sine wave and plays it

```haskell
osc1  <- createOscillator 200 0 Sine
gain1 <- createGain 0.5
 
connect $ osc1 .|. gain1 .||. eCtx

start osc1
```

### Other Examples

Code for examples are located in the `example/` folder.

To install:

```
cd examples/
cabal install
```

The resulting executables are located in `~/.cabal/bin/`

### Documentation

1. hackage
2. [Web Audio API documentation](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)