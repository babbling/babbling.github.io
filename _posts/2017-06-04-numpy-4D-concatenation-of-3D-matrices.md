---
title:  "Numpy 4D concatenation with 3D matrices"
date:   2017-06-04 00:00:00 -0600
categories: numpy matrix
category: numpy matrix
author:  Babbling Brook
---

**{{ page.title }}**

What happens when you have a series of RGB images where image is represented as a 3D Numpy array such as (32,32,3).

Now let's say you want to insert these into a single 4D Numpy array where the the first axis is the index for each image.
<!--more-->

We can initialize this new fourth dimension by referencing it with the None term as follows using numpy.concatenate:


```python
import numpy
mygray

print(mygray.shape)
newarray = mygray[None, :]
print(newarray.shape)
newarray = numpy.concatenate((newarray, mygray[None, :]), axis=0)
newarray = numpy.concatenate((newarray, mygray[None, :]), axis=0)
newarray = numpy.concatenate((newarray, mygray[None, :]), axis=0)
print(newarray.shape)
xtract = newarray[0,:,:]
plt.imshow(xtract, cmap='gray')
```

Here is an equivalent method using numpy.vstack:

```python
import numpy
mygray
print(mygray.shape)
newarray = mygray[None, :]
print(newarray.shape)
newarray = numpy.vstack((newarray, mygray[None, :]))
newarray = numpy.vstack((newarray, mygray[None, :]))
newarray = numpy.vstack((newarray, mygray[None, :]))
print(newarray.shape)
xtract = newarray[0,:,:]
plt.imshow(xtract, cmap='gray')
```

Here is an equivalent method using numpy.append:

```python
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
