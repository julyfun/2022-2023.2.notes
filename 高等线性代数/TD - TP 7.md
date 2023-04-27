## #method 如何求一个函数的对应矩阵

```ad-note
设函数为 f。只需要 [f(e1)], [f(e2)], [f(e3)] 就行
```

```python
def rot(u, theta):
    e = u / u.norm()
    # 先造一个全 0 矩阵是不错的主意捏
    r_mat = sp.zeros(3, 3)
    for j in range(3):
        cj = sp.Matrix([int(i == j) for i in range(3)])
        # 第 j 列填充方法
        r_mat[:, j] = e.dot(cj) * e + sp.cos(theta) * (cj - e.dot(cj) * e) \
            + sp.sin(theta) * e.cross(cj)
    return r_mat
```

```python
theta = sp.symbols('theta', real=True) 
rot(sp.Matrix([1, 0, 0]), theta)
```

![[Pasted image 20230330162549.png]]

## #def def de application affine 仿射变换的定义

![[Pasted image 20230330171037.png]]

## #def nature - 函数的 nature

Dire f est quelle trasformation usuelle?
指的是你要在下面几个里面选一个：
translation
rotation
identité
syméterie orthogonal
projection orthogonal

## #theo 旋转矩阵的行列式为 $1$


## #def automorphisme 自同构

#def isomorphisme 同构
#def endomorphisme 自同态

我们把 f 称作 E 到 E′ 的线性映射。
当线性映射从向量空间到它本身称作自同态;
当线性映射是双射时称作同构;
当线性映射同时满足自同态和同构时称作自同构;
当线性映射是从向量空间到它所对应的域 K 时称作线性泛函。

## reconnaître 题型

1. Soit les rotations de $\mathbb{R}^3$

$$R_{(1,1,1),(1,0,0),\pi/3}\quad\text{et}\quad R_{(1,1,1),(0,1,0),\pi/4}$$

reconnaître la composée

$$R_{O,(1,0,0),\pi/3}\circ R_{(1,1,1),(0,1,0),\pi/4}$$

```ad-note
这是要干啥捏
```

b 1