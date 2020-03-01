

```python
import pandas as pd

X = pd.DataFrame({'category': ['Cleaning', 'Cleaning', 'Entertainment', 'Entertainment', 'Tech', 'Tech'],
                        'store': ['Walmart', 'Dia', 'Walmart', 'Fnac', 'Dia','Walmart']})
```


```python
N = 10
cols = ['col_%d' % d for d in range(N)]
```


```python
def hash_fn(x):
    tmp = [0 for _ in range(N)]
    for val in x.values:
        tmp[hash(val) % N] += 1  
        print("{}: \t{} \t{}".format(val, hash(val), hash(val) % N))
    
    print("{}\n".format(tmp))
        
    return pd.Series(tmp, index=cols)
```


```python
X
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>category</th>
      <th>store</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Cleaning</td>
      <td>Walmart</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cleaning</td>
      <td>Dia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Entertainment</td>
      <td>Walmart</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Entertainment</td>
      <td>Fnac</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Tech</td>
      <td>Dia</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Tech</td>
      <td>Walmart</td>
    </tr>
  </tbody>
</table>
</div>




```python
res = X.apply(hash_fn, axis = 1)
```

    Cleaning: 	2757853755239877974 	4
    Walmart: 	954132345483583663 	3
    [0, 0, 0, 1, 1, 0, 0, 0, 0, 0]
    
    Cleaning: 	2757853755239877974 	4
    Walmart: 	954132345483583663 	3
    [0, 0, 0, 1, 1, 0, 0, 0, 0, 0]
    
    Cleaning: 	2757853755239877974 	4
    Dia: 	-6914920821674701215 	5
    [0, 0, 0, 0, 1, 1, 0, 0, 0, 0]
    
    Entertainment: 	-8470121183086974585 	5
    Walmart: 	954132345483583663 	3
    [0, 0, 0, 1, 0, 1, 0, 0, 0, 0]
    
    Entertainment: 	-8470121183086974585 	5
    Fnac: 	-1687995386747530867 	3
    [0, 0, 0, 1, 0, 1, 0, 0, 0, 0]
    
    Tech: 	3426699838082966844 	4
    Dia: 	-6914920821674701215 	5
    [0, 0, 0, 0, 1, 1, 0, 0, 0, 0]
    
    Tech: 	3426699838082966844 	4
    Walmart: 	954132345483583663 	3
    [0, 0, 0, 1, 1, 0, 0, 0, 0, 0]
    
    


```python
res
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>col_0</th>
      <th>col_1</th>
      <th>col_2</th>
      <th>col_3</th>
      <th>col_4</th>
      <th>col_5</th>
      <th>col_6</th>
      <th>col_7</th>
      <th>col_8</th>
      <th>col_9</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>


