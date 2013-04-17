Claudia is a simplistic python library for reading Cloudy output files

# Example

In this example, we read in a Cloudy model called "hii_test", and then plot the emissivity of the Hα and [O I] lines as a function of the neutral hydrogen fraction. 

```python
from claudia import CloudyModel
import matplotlib.pyplot as plt
m = CloudyModel("hii_test")
plt.plot(m.ovr.HI, m.em.H__1__6563A, label="H alpha")
plt.plot(m.ovr.HI, m.em.O__1__6300A, label="[O I] 6300")
plt.xlabel("Neutral hydrogen fraction")
plt.ylabel("log_10 (Emissivity)") 
plt.savefig("hii_test_plot.png")
```

The input file for "hii_test" can be found in the `examples/` folder. 

# How it works

The claudia library consists of a single class, `CloudyModel`, which is optimized for the most common use case, although it does have limited facilities for customization.  It reads all the Cloudy output files into a single structure, which can than be accessed as attributes.  
