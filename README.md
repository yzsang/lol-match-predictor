# lol-predictor

使用机器学习方法，基于英雄联盟高分段玩家比赛的前10分钟数据，预测蓝方是否能获胜。项目涵盖数据探索、特征工程、多模型比较、XGBoost调参和SHAP可解释性分析。

---

## 项目目标

- 使用前10分钟的对局特征预测比赛胜负结果（蓝方胜or负）
- 比较多种分类模型的性能（Logistic Regression、Random Forest、SVM、KNN、XGBoost）
- 对最佳模型进行GridSearch调参
- 使用SHAP分析模型的特征重要性，解释模型行为

---

## 模型表现

- 最佳模型：XGBoost（调参后）
- 测试集 F1 分数：**0.717**
- 最重要特征：蓝方与红方的金币差、经验差、小龙控制情况

---

## 项目文件说明

- `eda_modeling.ipynb`：主Notebook，包含完整的数据处理、建模与分析过程
- `requirements.txt`：项目依赖库列表（适用于 pip）
- `environment.yml`：conda 环境导出文件（推荐使用）
- `data/`：数据文件夹（本地运行需从Kaggle下载）

---

## 数据来源

- [Kaggle - League of Legends Diamond Ranked Games (10 min)](https://www.kaggle.com/datasets/bobbyscience/league-of-legends-diamond-ranked-games-10-min)

---

## 如何运行

1. 克隆本项目到本地
2. 创建并激活环境：
   - `conda env create -f environment.yml`
   - `conda activate lol-predictor`
3. 使用 JupyterLab 打开 `eda_modeling.ipynb` 并从头运行所有代码单元

---

## 后续优化方向

- 加入英雄选择/BP数据作为额外特征
- 使用完整对局数据进行时序建模（如RNN）