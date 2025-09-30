## aanmaken van vectoren
```python
np.array([1, 2, 3, 4, 5])      # array([1, 2, 3, 4, 5])
np.zeros(5)                    # array([0., 0., 0., 0., 0.])
np.ones(4)                     # array([1. ,1., 1., 1.])
np.arange(3,8)                 # array([3, 4, 5, 6, 7])
np.linspace(0, 1, 5)           # array([0., 0.25, 0.5, 0.75, 1.])
np.empty(2)                    # array([8.7..e-312, 2.4..e-312])
np.full(4, 42)                 # array([42, 42, 42, 42])
```
## matrices 
Een aantal methodes kunnen ook gebruikt worden om matrices aan te maken.
```python
np.zeros((3,4))
np.array([[1, 2, 3], [4, 5, 6]]) # 2 x 3 matrix
```

### attributen
```python
a = np.array([[1.0, 2.0, 3.0], [4.0, 5.0, 6.0]])
a.dtype                             # dtype('float64')
a.shape                             # (2, 3)
np.zeros(5).dtype                   # dtype('float64')
np.zeros(5, dtype=pn.int32).dtype   # dtype('int32')
np.zeros(5).shape                   # (5,)
np.arange(3,8).dtype                # dtype('int32')
```
Het default datatype is altijd `float64`tenzij expliciet opgegeven bij constructie.
```python
a.shape                             # (2, 3)
a.size                              # 6
a.ndim                              # 2
```

## Random
```python
rng = np.random.default_rng()
vals = rng.standard_normal(3)
vals              # array([1.55260998, -0.38395445, 0.45356297])
more_vals = rng.standard_normal(3)
more_vals         # array([-1.28386608, -0.87713461, -0.45373589])

# Ook matrices
rng.standard_normal((7,4)).shape # (7,4) 
```

## Bewerkingen
```python
a = np.array([14, 23, 32])
b = np.array([5, 4, 3])
a + b      # array([19, 27, 35])
a - b      # array([9, 19, 29])
a * b      # array([70, 92, 96])
a / b      # array([2.8, 5.75, 10.6666667])
a // b     # array([2, 5, 10])
a % b      # array([4, 3, 2])
a ** b     
```

### broadcasting
Wanneer 2 arrays niet dezelfde shape hebben zal numpy toch proberen om een resultaat te bekomen. *zie cursus*

## Indexeren van arrays
### indexeren ééndimensionale arrays
gelijkaardig aan python lijsten
```python
a = np.array([1, 5, 3, 19, 13, 7, 3])
a[3]     # 19
a[1:3]   # array([5,3])
a[2:-1]  # array([3, 19, 13, 7])
a[:3]    # array([1, 5, 3])
a[2::2]  # array([3, 13, 3])
a[::-1]  # array([3, 7, 13, 19, 3, 5, 1])
```
via indexering kun je ook elementen wijzigen. !Let op! slices van een `ndarray`zijn views op dezelfde onderliggende data. Als je dit niet wil maak dan eerst een copy.
```python
a_slice = a[2:6].copy()
```

### indexeren meerdimensionale arrays
```python
b = np.arange(12).reshape(3,4)
b   # array([[0, 1, 2, 3],
    #        [4, 5, 6, 7],
    #        [8, 9, 10, 11]])
b[1, 2] # 6
b[1, :] # array([4, 5, 6, 7])
b[:, 1] # array([1, 5, 9])
```

Met fancy indexing kan je ook een lijst of tupel meegeven van de rijen of kolommen waarin je geïnteresseerd bent.
```python
b[(-1,0), 1:3] 
# array([[9, 10],
#        [1, 2]])
```
![[Pasted image 20250930094608.png]]
## Aggregatiemethoden
Methoden die één of andere aggregatie (samenvatting) berekenen van de elementen.
```python
a = np.arange(6).reshape(2,3)
a      # array([[0, 1, 2],
       #        [3, 4, 5]])
np.sum(a)       # 15
# Bereken de som in de richting van de axis 0, houd axis 1 over
np.sum(a, axis=0)  # array([3, 5, 7])
# Bereken de som in de richting van de axis 1, houd axis 0 over
np.sum(a, axis=1)  # array([3, 12])
np.sum(a, axis=1, keepdims=True)  # array([[ 3],
                                  #        [12]])
```

