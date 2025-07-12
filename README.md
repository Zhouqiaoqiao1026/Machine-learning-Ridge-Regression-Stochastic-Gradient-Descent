# Energy Consumption Prediction with Ridge Regression and SGD



## 概述

使用岭回归（Ridge Regression）和随机梯度下降（Stochastic Gradient Descent）来预测低能耗建筑中家用电器的能耗。项目实现了从数据加载、预处理、模型训练到评估的完整机器学习流程，所有核心算法（包括梯度下降优化器）均从零实现。



## 关键步骤

1. **数据准备**：
   - 从UCI机器学习仓库下载能源消耗数据集
   - 添加工作日/周末二元特征
   - 删除无关特征（日期和随机变量）

2. **数据预处理**：
   - 将数据分为训练集(70%)、验证集(15%)和测试集(15%)
   - 标准化连续特征（均值为0，标准差为1）
   - 保留二元特征原始值

3. **模型训练**：
   - 实现随机梯度下降优化器
   - 使用网格搜索寻找最优超参数：
     - λ（正则化强度）：0.0001
     - η（学习率）：0.01
     - S（小批量大小）：152

4. **模型评估**：
   - 在测试集上计算RMSE：98.70

## 依赖项

运行此项目需要以下Python库：

- numpy
- pandas
- matplotlib
- urllib

安装依赖：

```bash
pip install numpy pandas matplotlib
```



## 结果

在最优超参数组合下（λ=0.0001, η=0.01, S=152），模型在测试集上达到了98.70的RMSE。这表明模型能够以平均约98.7Wh的误差预测电器能耗。



## 关键函数

- `sgd_optimiser()`: 随机梯度下降优化器实现
- 数据标准化流程
- 超参数网格搜索实现



## 数据集来源

[UCI Appliances energy prediction dataset](https://archive.ics.uci.edu/ml/datasets/Appliances+energy+prediction)
