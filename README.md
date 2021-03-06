# Notes for  Machine Learning



### 前言  

	  这个笔记是根据西瓜书的整本内容做一个总结(机器学习-周志华)，作为一个理论基础，供日后自己查看。也可以帮助一些机器学习爱好者总结知识点。



### 第一章 绪论

	1.样本：数据集中一条记录
	
	2.特征：样本所具有的一些性质(这个瓜真甜,甜就是一种特征)
	
	3.特征向量：一个样本可以被多个特征所描述，如果一个苹果有2个特征(大小，口感),将这两个  特征分别作为x轴和y轴，那么其中一个苹果(中号，脆)就可以用二维坐标系上的一个点表示，这个点   有自己的坐标，这个点还对应一个坐标向量(基于原点),这个向量称为特征向量。(可以类比到三维或者更高的维度)  
	
	4.label:属于样本的一条属性比如两个水果f1(大小=大号，口感=甜，质量=好),f2(大小=小号，口  感=酸，质量=坏)，其中“好”和“坏’就是f1和f2的label它们的标签。后面的监督学习和无监督学习就  是根据否存在label属性做评判的
	
	5.机器学习两个主要大问题：
	
		(1)分类：

 			如果要预测的是离散值（好瓜，坏瓜），这就是分类问题。将一堆样本分成不同的类 别就是分类问题。如果是是分成两类就是**二分类**，通过称其中一类为 **正类 **，另一类为 **反类**，分成多个类别叫做多分类。

		(2)回归：
	
			如果预测的连续值，(如到多少年后，房价会是多少)，这就是回归问题。将一堆数据样本放入模型后，会拟合出一条曲线，我们输入x就可以得到其对应的输出。
	
	6.监督学习：训练样本中有label标记信息。分类和回归是其中的代表
	
	7.非监督学习：训练样本中没有label标记信息。聚类是其中的代表。聚类：将训练集分成若干组，每个组成为一个 **簇(**cluster),这些簇会对可能潜在的概念进行划分。如将西瓜分成本地瓜，外地瓜，这样的学习过程可以帮助我们了解数据内在的规律。在学习过程中不包含label标记
	
	8.假设空间：可以把学习过程看成一个在所有假设组成的空间中进行搜索的过程，搜索目标是找到与训练集匹配(fit)的假设。



### 第二章 模型评估与选择

	1.错误率(百分比显示)：分类错误的样本数占总样本数的比例称为错误率(error rate) 
	
	2.精度(百分比显示)：同理 精度=1-错误率
	
	3.误差：利用模型学习后的输出与样本真实输出值的差异。其中在训练集上的误差叫做训练误差，在新的样本(需要预测的)上的误差叫做泛化误差
	4.过拟合:将训练数据学习的太好，但不能反映该数据在整个集合(所有该数据，比如训练集和要预测的样本集)上的普遍规律(学习能力较强)
	
	5.欠拟合：对训练样本的一般性质尚未学习好(学习能力差，在决策树中扩展分支，在神经网络中增加轮数)
	
	6.留出法：分成2个 数据集 一个训练集 ，一个测试集
	
	7.交叉验证法：先将数据集分成k个子集，然后取出每个子集的一部分求并集，作为整个数据集的训练集，每个子集剩下的部分求并集作为测试集
	
	8.性能度量：衡量模型的泛化能力(模型在新样本上的表现)
	
	9.均方误差:回归问题最常用的性能度量。(loss函数)
	10.错误率与精度：分类问题常用的性能度量
	
	11.查准率、查全率、F1：
		对于二分类问题，可将样例根据其真是类别分与学习器预测类别的组合划分成真正例，假正例，真反例，假反例四种情况。


![img](file:///C:\Users\macbook\AppData\Roaming\Tencent\Users\944593288\QQ\WinTemp\RichOle\GZYJX{[6U_T[$ZFAP}RZ~%9.png)

		其中TP就是我们要差的类别(比如好瓜)。一般来说，查准率高时，查全率往往偏低，而查全率高时，查准率往往偏低。



	12.ROC与AUC
	
		很多学习器为样本产生一个实值或概率预测，然后将这个值与分类阈值进行比较，如果大于阈值为正类，小于阈值为反类。
	
		ROC：受试者工作特征
	
		AUC(Area Under ROC  Curve) ROC曲线下面的面积

### 第三章 线性模型

	1.f(x) = wx+b 其中特征值的值已知，若确定w和b的值那么模型就确定

	2.在公式中Wi表示的当前xi的特征的权重，好瓜=0.2*色泽+0.5*根蒂+0.3*敲声，其中根蒂权重最大，最为重要。

	3.利用均方误差求出f(x)与真实值之间的误差，基于均方误差最小化来求解模型叫做**最小二乘法**。

	4.**对数线性回归**，用y的衍生物取逼近真实值

	5.用线性模型做分类问题，通过**单位阶跃函数**，线性模型得到的值是一个实值，如果该值大于0则 取1，如果等于0  则取0.5，如果小于0 则取0

	6.**Sigmoid函数**，因为单位阶跃函数是不连续的，理论计算不方便，所以选取一个功能类似，但连续的函数 **对数几率函数 **是一种Sigmoid函数。

	7.




















































































































































































































































































































































	