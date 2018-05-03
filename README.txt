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

pytorch_v10 基于版本v7，之前设计的代码有问题，最后一层不能对两个句子分开处理，应当一起处理，保持参数一致
            第一层self_attention要不要一起处理，暂时不确定（暂时分开处理）
            GPU版本的v10句子长度为50（在小鹿的电脑上运行）

pytorch_v11 对self-attention进行更改，我们不使用该self-attention层，新定义一个层，称之为filter_layer

pytorch_v_test 基于v4修改代码，主要是实现global attention和local attention

tensorflow_v3 
根据pytorch第三版更改的tensorflow版本