# ROC 
## Convex Hull
ROC 把多个Curve (False Positive和True Positive) 来结合，对比展示模型性能，
Convex Hull是凸包，凸包越大，意味着模型True Positive的部分对比False Positive越大，模型越好，用来选择最佳操作点

## ROC Properties 
AUC-ROC 是ROC曲线下面的面积，用于衡量分类器在正负类别的整体性能

# Last Year Exam Question
C1 and C2, Which is better? 
# PR vs. ROC

PR曲线重点关注模型在正类上的性能。

1. **Precision（精确率）**：
    
    - Precision是指模型正确预测为正类的样本占所有预测为正类样本的比例。
    - 公式为：Precision = True Positives / (True Positives + False Positives)。
2. **Recall（召回率）**：
    
    - Recall是指模型正确预测为正类的样本占所有实际正类样本的比例。
    - 公式为：Recall = True Positives / (True Positives + False Negatives)。
- 当你关注正类（如罕见疾病的诊断、欺诈检测等）的检测性能时，PR曲线是一个非常有用的工具。
- 在类别高度不平衡的数据集中，PR曲线比ROC曲线更能提供有用的性能度量。