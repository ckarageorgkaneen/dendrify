TODOs:

- Encapsulate brian objects in the same way brian encapsulates other libraries (e.g. numpy, matplotlib)
e.g.
```python
import brian2 as b
from brian2.units import (ms, um, pA, nS, uS, ohm, cm, mV, uF, mvolt)
from dendrify import Soma, Dendrite, NeuronModel

b.prefs.codegen.target = 'numpy'
b.start_scope()    # allows running separate simulations in the same notebook
```
should be:
```python
import dendrify as d
from dendrify.units import (ms, um, pA, nS, uS, ohm, cm, mV, uF, mvolt)
d.prefs.codegen.target = 'numpy'
d.start_scope()
```
- Replace NeuronModel - NeuronGroup linking scheme. NeuronModel should superclass NeuronGroup:
name, size, etc. should all be defined explicitly upon construction, just like one does for NeuronGroup.
- Replace printing with logging (see https://stackoverflow.com/a/6918596)
- Replace sys.exit() with raising a case-specific error
- Allow single-compartment neurons
- Make `pre` an arg (mandatory)