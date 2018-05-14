pytorch_v3 来自于我的笔记本电脑的第三版

pytorch_v4 对输出进行修改，输出是每个perspective的平均，而不是简单的连接
           对attention layer的输出也进行修改，不是简单的连接，让其进行element-wise相乘，结果向量最为输出向量
           在自己电脑上效果不是很好
           在这个实验室电脑上
           
             File "E:\Quora\model_pytorch_v4\self_att_layer.py", line 183, in regional_self
           _att
                att[s : s+r] = 1
           ValueError: result of slicing is an empty tensor

pytorch_v5 来自于电脑，对GRU的参数进行了修改

pytorch_v6 来自于电脑

pytorch_v7 对代码做一些更改，基于自己电脑上的v6版本，对最后一层进行maxpooling
           电脑上的v7将句子长度更改为50

pytorch_v8 考虑不使用self-attention-layer，基于v7进行更改

pytorch_v9 复现笔记本电脑上的tensorflow_v7
           完全复现笔记本电脑上的v7，最后一层也一致（在笔记本电脑上跑）

pytorch_v10 基于版本v7，之前设计的代码有问题，最后一层不能对两个句子分开处理，应当一起处理，保持参数一致
            第一层self_attention要不要一起处理，暂时不确定（暂时分开处理）
            GPU版本的v10句子长度为50（在小鹿的电脑上运行，已经结束）

pytorch_v11 对self-attention进行更改，我们不使用该self-attention层，新定义一个层，称之为filter_layer（最好，0.84）
            新加入一个参数，利用LSTM，还没有运行（小鹿，）

pytorch_v12 base_on v11, add fusion_layer
	    不加fusion_layer，多一层gru，其输出用于self-attention，self_attention也做相应改变
            更改，去掉gru,目前结构为：filter(different from v11), gru, agg, gru, struc, max/mean pooling  dot, global(在小鹿电脑上，0.83）
													  general,global（在小鹿电脑上，效果不好）
													  dot, global（在小鹿电脑上重新跑,0.83）
            将LSTM也加进去，还没有测试filter, lstm, agg, lstm, struc, max/mean pooling  dot, global（小鹿，）

pytorch_v13 基于v12，对最后一层进行更改，暂时不用structured_attention，基于tensorflow_v7
            更改，结构：filter(from v11),gru, agg, gru, struc, max/mean pooling, dot, global(在小鹿电脑上，0.83）
                                                                                 general,global（在小鹿电脑上，未测试，不知道效果，重新跑）
										 dot, global（在小鹿电脑上重新跑,0.83）
            将GRU换为LSTM，filter,lstm,agg,lstm,struc,max/maen pooling  dot, global（小鹿，）

pytorch_v14 基于v11，队aggregation_layer进行修改，参考笔记(笔记上的还没有实现，暂时利用cosine距离)，
            在实验室电脑上跑，效果看似还行0.83，电脑崩了，在小鹿电脑上跑0.83

pytorch_v15 基于v11，对aggregation_layer进行修改，参考笔记（在笔记本上跑，比较慢，效果也一般，已暂停）
            准备在小鹿电脑上跑，还没跑

pytroch_v16 对aggregation的regional attention 进行更改，使其更合理（还未完成，已完成，还未运行）

pytorch_v17 同样对aggregation进行处理，对attention部分进行处理，结合 词与词之间的attention，以及 词与句子间的attention

pytorch_v_test 基于v4修改代码，主要是实现global attention和local attention

tensorflow_v3 
根据pytorch第三版更改的tensorflow版本