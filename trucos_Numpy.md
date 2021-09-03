# Trucos de Numpy

## Probando todos los trucos

### ¿Campo de aplicación de la librería Numpy?
Numpy es una librería muy importante para Python ya que es la base de todos los cálculos científicos y muchas de las librerías de Machine Learning.

Numpy reemplaza de forma más eficiente lo que podría ser un tipo lista. En las listas podemos tener conjuntos de elementos numéricos. Sin embargo las listas no logran manejar datos de dos dimensiones.


```python
import numpy as np
```

## Arrays

#### Creando Arrays


```python
a = np.array([1,2,3])
b = np.array([(1.5,2,3), (4,5,6)], dtype = float)
c = np.array([[(1.5,2,3), (4,5,6)], [(3,2,1), (4,5,6)]], dtype = float)
```

#### Creand Array de ceros


```python
np.zeros((3,4)) 
```




    array([[0., 0., 0., 0.],
           [0., 0., 0., 0.],
           [0., 0., 0., 0.]])



#### Creando Array de unos


```python
np.ones((2,3,4),dtype=np.int16)
```




    array([[[1, 1, 1, 1],
            [1, 1, 1, 1],
            [1, 1, 1, 1]],
    
           [[1, 1, 1, 1],
            [1, 1, 1, 1],
            [1, 1, 1, 1]]], dtype=int16)



#### Creando Array uniforme


```python
d = np.arange(10,25,5)
np.linspace(0,2,9) 
```




    array([0.  , 0.25, 0.5 , 0.75, 1.  , 1.25, 1.5 , 1.75, 2.  ])



#### Creando Array constante


```python
 e = np.full((2,2),7)
```

#### Creando matriz 2x2


```python
 f = np.eye(2)
```

#### Creando Array con valores aleatorios


```python
np.random.random((2,2))
```




    array([[0.82881737, 0.68432412],
           [0.29925142, 0.67308616]])



#### Creando un Array vacío


```python
np.empty((3,2)) 
```




    array([[0., 0.],
           [0., 0.],
           [0., 0.]])



## Guardando y cargando de disco


```python
np.save('my_array', a)
```


```python
 np.savez('array.npz', a, b)
```


```python
 np.load('my_array.npy')
```




    array([1, 2, 3])



## Guardando y cargando texto plano


```python
np.loadtxt("numbers.txt")
```




    array([ 25.,  10., 100.])




```python
 np.genfromtxt("archivoSVC.csv", delimiter=',')
```




    array([nan, 90., 20.])




```python
np.savetxt("myarray.txt", a, delimiter=" ")
```

## Tipos de datos

    1.Tipos enteros de 64 bits firmados
    2.Coma flotante estándar de doble precisión
    3.Números complejos representados por 128 flotadores
    4.Tipo booleano que almacena valores TRUE y FALSE
    5.Tipo de objeto Python
    6.Tipo de cadena de longitud fija
    7.Tipo unicode de longitud fija


```python
print("1")
np.int64
```

    1
    




    numpy.int64




```python
print("2")
np.float32
```

    2
    




    numpy.float32




```python
print("3")
np.complex
```

    3
    




    complex




```python
print("4")
np.bool
```

    4
    




    bool



print("5")
np.object


```python
print("6")
np.string_
```

    3
    




    numpy.bytes_




```python
print("7")
np.unicode_
```

    7
    




    numpy.str_



## Inspeccionando los arreglos


```python
print("1.Dimensión del arreglo = ", a.shape)
print("2.Tamaño del arreglo = ", len(a))
print("3.Número de dimensiones del arreglo = ", b.ndim)
print("4.Número de elementos en el arreglo = ", e.size)
print("5.Tipo de datos de los elementos del arreglo = ", b.dtype)
print("6.Nombre de los tipos de datos = ", b.dtype.name)
print("7.Convertir un array a otro tipo de dato => \n", b.astype(int))
```

    1.Dimensión del arreglo =  (3,)
    2.Tamaño del arreglo =  3
    3.Número de dimensiones del arreglo =  2
    4.Número de elementos en el arreglo =  4
    5.Tipo de datos de los elementos del arreglo =  float64
    6.Nombre de los tipos de datos =  float64
    7.Convertir un array a otro tipo de dato => 
     [[1 2 3]
     [4 5 6]]
    

## Pidiendo ayuda


```python
np.info(np.ndarray.dtype)
```

    Data-type of the array's elements.
    
    Parameters
    ----------
    None
    
    Returns
    -------
    d : numpy dtype object
    
    See Also
    --------
    numpy.dtype
    
    Examples
    --------
    >>> x
    array([[0, 1],
           [2, 3]])
    >>> x.dtype
    dtype('int32')
    >>> type(x.dtype)
    <type 'numpy.dtype'>
    

## Arrglos matemáticos

### Operaciones aritméticas


```python
print("Sustracción")
g = a - b
np.subtract(a,b)
```

    Sustracción
    




    array([[-0.5,  0. ,  0. ],
           [-3. , -3. , -3. ]])




```python
print("Adición")
b + a
np.add(b,a)
```

    Adición
    




    array([[2.5, 4. , 6. ],
           [5. , 7. , 9. ]])




```python
print("División")
a / b 
np.divide(a,b)
```

    División
    




    array([[0.66666667, 1.        , 1.        ],
           [0.25      , 0.4       , 0.5       ]])




```python
print("Multiplicación")
a * b
np.multiply(a,b)
```

    Multiplicación
    




    array([[ 1.5,  4. ,  9. ],
           [ 4. , 10. , 18. ]])




```python
print("Exponente")
np.exp(b)
```

    Exponente
    




    array([[  4.48168907,   7.3890561 ,  20.08553692],
           [ 54.59815003, 148.4131591 , 403.42879349]])




```python
print("Raiz")
np.sqrt(b)
```

    Raiz
    




    array([[1.22474487, 1.41421356, 1.73205081],
           [2.        , 2.23606798, 2.44948974]])




```python
print("Seno del arreglo")
np.sin(a)
```

    Sin del arreglo
    




    array([0.84147098, 0.90929743, 0.14112001])




```python
print("Coseno del arreglo")
np.cos(b)
```

    Coseno del arreglo
    




    array([[ 0.0707372 , -0.41614684, -0.9899925 ],
           [-0.65364362,  0.28366219,  0.96017029]])




```python
print("Logaritmo del arreglo")
np.log(a)
```

    Logaritmo del arreglo
    




    array([0.        , 0.69314718, 1.09861229])




```python
print("Producto del arreglo")
e.dot(f)
```

    Producto del arreglo
    




    array([[7., 7.],
           [7., 7.]])



## Comparaciones


```python
a == b
```




    array([[False,  True,  True],
           [False, False, False]])




```python
a < 2
```




    array([ True, False, False])




```python
np.array_equal(a, b)
```




    False



## Agregar funciones


```python
print("La suma del array es : ", a.sum())
```

    La suma del array es :  6
    


```python
print("El valor mínimo del arreglo es : ", a.min())
```

    El valor mínimo del arreglo es :  1
    


```python
print("El valor máximo de una columna del array es : ", b.max(axis=0))
```

    El valor máximo del array es :  [4. 5. 6.]
    


```python
print("Suma acumulativa de los elementos del arreglo : ", b.cumsum(axis=1))
```

    El valor máximo de una columna del array es :  [[ 1.5  3.5  6.5]
     [ 4.   9.  15. ]]
    


```python
print("Media : ", a.mean())
```

    Media :  2.0
    


```python
b.median ()
a.corrcoef ()
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-137-f693eccd7167> in <module>
    ----> 1 b.median ()
          2 a.corrcoef ()
    

    AttributeError: 'numpy.ndarray' object has no attribute 'median'



```python
print("Desvición estndAr: ", np.std(b))
```

    Desvición estndr:  1.5920810978785667
    

## Copiando arreglos


```python
h = a.view()
```


```python
np.copy(a)
```




    array([1, 2, 3])




```python
h = a.copy()
print(h)
```

    [1 2 3]
    

## Ordenando arreglos


```python
a.sort()
c.sort(axis=0)
```

## Subconfiguración, segmentación, indexación


```python
print("Subconfiguración")
a[2]
```

    Subconfiguración
    




    3




```python
b[1,2]
```




    6.0



### Segmentación


```python
 a[0:2]
```




    array([1, 2])




```python
b[0:2,1]
```




    array([2., 5.])




```python
b[:1]
```




    array([[1.5, 2. , 3. ]])




```python
c[1,...]
```




    array([[3., 2., 3.],
           [4., 5., 6.]])




```python
 a[ : :-1]
```




    array([3, 2, 1])



### Indexando booleanos


```python
a[a<2]
```




    array([1])



### Indexación de fantasía


```python
b[[1, 0, 1, 0],[0, 1, 2, 0]]
```




    array([4. , 2. , 6. , 1.5])




```python
b[[1, 0, 1, 0]][:,[0,1,2,0]]
```




    array([[4. , 5. , 6. , 4. ],
           [1.5, 2. , 3. , 1.5],
           [4. , 5. , 6. , 4. ],
           [1.5, 2. , 3. , 1.5]])



## Manipulación de arreglos

### Transponer arreglos


```python
i = np.transpose(b)
```


```python
i.T
```




    array([[1.5, 2. , 3. ],
           [4. , 5. , 6. ]])



### Cambiando la forma del arreglo


```python
b.ravel()
```




    array([1.5, 2. , 3. , 4. , 5. , 6. ])




```python
g.reshape(3,-2)
```




    array([[-0.5,  0. ],
           [ 0. , -3. ],
           [-3. , -3. ]])



### Agregando y removiendo elementos


```python
h.resize((2,6))
```


```python
 np.append(h,g)
```




    array([ 1. ,  2. ,  3. ,  0. ,  0. ,  0. ,  0. ,  0. ,  0. ,  0. ,  0. ,
            0. , -0.5,  0. ,  0. , -3. , -3. , -3. ])




```python
 np.insert(a, 1, 5)
```




    array([1, 5, 2, 3])




```python
np.delete(a,[1])
```




    array([1, 3])



### Combinando arreglos


```python
np.concatenate((a,d),axis=0)
```




    array([ 1,  2,  3, 10, 15, 20])




```python
np.vstack((a,b))
```




    array([[1. , 2. , 3. ],
           [1.5, 2. , 3. ],
           [4. , 5. , 6. ]])




```python
np.r_[e,f]
```




    array([[7., 7.],
           [7., 7.],
           [1., 0.],
           [0., 1.]])




```python
np.hstack((e,f))
```




    array([[7., 7., 1., 0.],
           [7., 7., 0., 1.]])




```python
np.column_stack((a,d))
```




    array([[ 1, 10],
           [ 2, 15],
           [ 3, 20]])




```python
np.c_[a,d]
```




    array([[ 1, 10],
           [ 2, 15],
           [ 3, 20]])



### Separación de arreglos


```python
 np.hsplit(a,3)
```




    [array([1]), array([2]), array([3])]




```python
np.vsplit(c,2)
```




    [array([[[1.5, 2. , 1. ],
             [4. , 5. , 6. ]]]), array([[[3., 2., 3.],
             [4., 5., 6.]]])]


