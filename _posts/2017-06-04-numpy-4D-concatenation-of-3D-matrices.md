---
layout: post
title:  "Numpy 4D concatenation with 3D matrices"
date:   2016-06-04 00:00:00 -0600
categories: numpy matrix
category: numpy matrix
author:  Babbling Brook
---
What happens when you have a series of RGB images where image is represented as a 3D Numpy array such as (32,32,3)

Now let's say you want to insert these into a single 4D Numpy array where the the first axis is the index for each image.

We can initialize this new fourth dimension by referencing it with the None term as follows:

```
import numpy
mygray
print(mygray.shape)
newarray = mygray[None, :]
print(newarray.shape)
newarray = numpy.append(newarray, mygray[None, :], axis=0)
newarray = numpy.append(newarray, mygray[None, :], axis=0)
newarray = numpy.append(newarray, mygray[None, :], axis=0)
print(newarray.shape)
xtract = newarray[0,:,:]
plt.imshow(xtract, cmap='gray')
```

