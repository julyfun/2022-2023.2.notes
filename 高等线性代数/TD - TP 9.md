## T1 #method 特征向量近似

@chat
> 在数学上，$\widehat{E_n}$ 表示矩阵 $A$ 的一个特征向量近似，它是通过使用幂法（power method）得到的，其对应的特征值是 $\lambda_n$。
> 
> 为了找到 $\widehat{E_n}$ 和 $\lambda_n$，可以按照以下步骤进行：
> 
> 1.  选择一个任意的非零列向量 $\mathbf{v}_0$ 作为初始向量。
>     
> 2.  进行幂法迭代，即重复以下步骤直到收敛：
>     
>     -   计算 $A\mathbf{v}_k$。
>     -   计算 $|\lambda_n^{(k)}| = |\mathbf{Av}_k|_\infty$，其中 $|\cdot|_\infty$ 表示向量的无穷范数。
>     -   计算 $\mathbf{v}_{k+1} = \frac{A\mathbf{v}_k}{|\lambda_n^{(k)}|}$。
> 3.  将 $\mathbf{v}_k$ 规范化得到 $\widehat{E_n} = \frac{\mathbf{v}_k}{|\mathbf{v}_k|_2}$，其中 $|\cdot|_2$ 表示向量的 2-范数。
>     
> 4.  计算 $\lambda_n = \lambda_n^{(k)}$。
>     
> 
> 在每一次迭代中，可以检查 $|\lambda_n^{(k)} - \lambda_n^{(k-1)}|$ 是否小于预设的精度 $\epsilon$，如果满足条件就可以停止迭代。
> 
> 需要注意的是，幂法只能得到一个特征值和对应的特征向量，如果需要找到多个特征值和特征向量，可以使用反迭代法（inverse iteration）或QR算法（QR algorithm）等其他方法。

