GN-OA环境配置
numpy==1.24.3
torch==1.13.1
torch_geometric==2.0.2
dive-into-graphs==1.1.0
pyg-lib==0.2.0+pt20cu118
pymatgen==2023.8.10
torch==2.0.0
torch-cluster==1.6.3+pt20cu118
torch_geometric==2.5.2
torch-scatter==2.1.2+pt20cu118
torch-sparse==0.6.18+pt20cu118
torch-spline-conv==1.2.2+pt20cu118
torchaudio==2.0.0
torchvision==0.15.0

GN-OA框架
数据存储
- npy格式   np.save or np.load
- pt格式    torch.save or torch.load
- pkl格式   import pickle pickle.dump or pickle.load (保存任何格式)
- npz格式   np.save or np.load  (多种类型数据保存成字典格式)

1.选择ComENet图网络预测形成焓
- 数据集准备torch.tensor格式
  - 结构坐标R 每个原子坐标
  - 原子数Z
  - 结构中原子个数N 
- 数据集处理
  - transform 每次加载数据传入torch格式数据进行数据格式转化, e.g.归一化
  - pre_transform 在保存数据前进行一次预处理
  - pre_filter 选择只包含某些条件的数据
- 模型训练
  - 导入ComENet模型架构
  - 重新编写train与val函数
  - 超参数优化
  - 存储训练好的模型
- 模型预测
  - 加载模型
  - 预测形成焓性质
2.基于贝叶斯优化开展结构演化
- 结构分析
