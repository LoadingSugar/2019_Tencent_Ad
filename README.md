# 2019年腾讯广告 大赛

## 简单baseline（仅供参考，分数不高）
 - data_handle 数据处理和训练数据生成；部分曝光数据与测试数据广告id重合，抽取这部分数据直接用于填充测试结果
 - lgb_model hyperopt对lgb模型进行自动调参，训练数据，用3月18号数据测试模型SMAPE得分
 - lgb_model2 加特征，保证单调性得分，并填充测试集预测数据

## 临时文件和不同的训练集（path2路径下）
 - exp_all_label_minisday   静态操作里面的ad_id 曝光值，非当天，16号label就是17号的（预测值）
 - exp_all_label_nowday     静态操作里面的ad_id 曝光值，当天，16号label就是16号实际的
 - exp_his_label            B榜测试数据里面的ad_id 在曝光数据里统计出来的历史曝光数据（直接用于测试集基于规则的填充）
 - op_sta_all_df            静态数据和操作数据的集合（并对所有天数进行了填充）
 - train1_with0             训练数据包含label为0数据，0占70%多
 - train1_with0_delete      训练数据（删除部分不适用于训练的数据，16号训练数据，但17号对广告修改了的不算）包含label为0数据，0占70%多
 - train1_without0          训练数据包含label没有0数据
 - train1_without0_delete   训练数据包含label没有0数据（删除部分不适用于训练的数据，16号训练数据，但17号对广告修改了的不算）包含label为0数据，0占70%多
