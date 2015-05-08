# sivi - A toolpath generation python library for CNC machining

Instead of using a GUI to generate GCode, *sivi* allows you to write python code.
It's aims to be an Openscad-like for CAM.
 
## Features
- Composable operations
- Backlash compensation

## Install

## Quickstart

```python
from sivi.operations import *
from sivi.backend import GCodeBackEnd

b = GCodeBackEnd()
b.add_tool("1", tools.EndMill(d=3, l=42))
b.change_tool("1")

op1 = CircularPocket(diameter=10, step_over=0.5, interpolate=True) \
	.z_passes(z_end=-10, z_step=-0.5) \
	.circular_repetition(diameter=50, n=6, z_safe=1)

op1.run(backend=b, pos=(0,0,0), feed_rate=100, plunge_rate=10)
```

