# This is my first post!

As expected from someone who regularly uses LaTeX, I'll drop some nonsense equations just to see how they look :)

$$
\hat{H} = \frac1{2}\sum_{i=1}^N \sum_{j\neq i}^N \frac1{|r_i- r_j|}
$$

If we are to calculate this with python, then we'd do the following:
```python
def calc_Hhat(r):
""" r is the vector containing the positions of the electrons"""
    H = 0
    for i in range(N):
        for j in range(N):
            if i != j:
                H += 1./abs(r[i]-r[j])
    return H/2.
```

And that's it! Although you may want to consider that electrons `live in a 3D space`, so this denominatior should in fact be the L2 norm of a vector difference, but that'll do for the moment.
