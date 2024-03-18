1. Install
   - Download and unzip the folder at the point in which you wish to install the module
   - cd into the directory. There is a setup.py file. Execute the command
          " python3 -m pip install -e . "
     to setup the module. 

2. Usage
   The code can be imported in a python script as
   ```python
   import matplotlib.pyplot as plt
   import numpy as np
   import sisl
   from grainboundarystructures.GB import load_GB_TS_relax as load
   gbs = load(); # 218 GBs, but some duplicates
   gb  = gbs[150]
   gem,gep,gd=gb['EM'],gb['EP'],gb['D']# electrodes and device
   print(gem,gep,gd)
   plt.scatter(gd.xyz[:,0], gd.xyz[:,1])
   plt.scatter(gem.xyz[:,0], gem.xyz[:,1])
   plt.scatter(gep.xyz[:,0], gep.xyz[:,1])
   plt.axis('equal'); plt.show()
```
