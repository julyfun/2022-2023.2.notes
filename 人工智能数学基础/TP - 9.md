## #method KNN 算法

### 算法
给定一个训练数据集，对新输入的实例，在训练数据集中找到与该实例最邻近的k个实例，在这k个实例，多数属于某个类别，就把该输入实例划分为这个类别。

### python 中的位置
```python
from sklearn.neighbors import KNeighborsClassifier as KNN
```
### 用法
- `.fit(x, y)`：x 传入格式为 np.ndarray，shape 为 数据量 × 特征数。当以 csv 读入时，每行是一个完整数据。y 传入格式为 数据量
![[Pasted image 20230414182622.png]]
- `.predict()` 传入格式为 shape 为 1 × 特征数
```python
pass
knn = KNN(n_neighbors=5)
x_train = data.to_numpy()[:, 1:]
data_array = data.to_numpy()
x_train = np.concatenate((data_array[:18, 1:], data_array[19:, 1:]), axis=0)
# x_train
print(x_train.shape)
# type(data.to_numpy())

y_train = catego
print(y_train.shape)
knn.fit(x_train, y_train)
x_test = data_array[18, 1:]
x_test = x_test.reshape((1, -1))
print(x_test.shape)
print(knn.predict(x_test))
```

```python
(35, 12)
(35,)
(1, 12)
[3]
```

## #method Python 中 np.ndarray 的拼接

```python
x_train = np.concatenate((data_array[:18, 1:], data_array[19:, 1:]), axis=0)
```

这份代码删除了第 18 行的数据，也删除了第 0 列的数据

面纹金丝熊和波利金丝熊有何区别？