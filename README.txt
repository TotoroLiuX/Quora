pytorch_v3 �������ҵıʼǱ����Եĵ�����

pytorch_v4 ����������޸ģ������ÿ��perspective��ƽ���������Ǽ򵥵�����
           ��attention layer�����Ҳ�����޸ģ����Ǽ򵥵����ӣ��������element-wise��ˣ����������Ϊ�������
           ���Լ�������Ч�����Ǻܺ�
           �����ʵ���ҵ�����
           
             File "E:\Quora\model_pytorch_v4\self_att_layer.py", line 183, in regional_self
           _att
                att[s : s+r] = 1
           ValueError: result of slicing is an empty tensor

pytorch_v5 �����ڵ��ԣ���GRU�Ĳ����������޸�

pytorch_v6 �����ڵ���

pytorch_v7 �Դ�����һЩ���ģ������Լ������ϵ�v6�汾�������һ�����maxpooling
           �����ϵ�v7�����ӳ��ȸ���Ϊ50

pytorch_v8 ���ǲ�ʹ��self-attention-layer������v7���и���

pytorch_v9 ���ֱʼǱ������ϵ�tensorflow_v7
           ��ȫ���ֱʼǱ������ϵ�v7�����һ��Ҳһ�£��ڱʼǱ��������ܣ�

pytorch_v10 ���ڰ汾v7��֮ǰ��ƵĴ��������⣬���һ�㲻�ܶ��������ӷֿ�����Ӧ��һ�������ֲ���һ��
            ��һ��self_attentionҪ��Ҫһ������ʱ��ȷ������ʱ�ֿ�����
            GPU�汾��v10���ӳ���Ϊ50����С¹�ĵ��������У��Ѿ�������

pytorch_v11 ��self-attention���и��ģ����ǲ�ʹ�ø�self-attention�㣬�¶���һ���㣬��֮Ϊfilter_layer����ã�0.84��
            �¼���һ������������LSTM����û�����У�С¹����

pytorch_v12 base_on v11, add fusion_layer
	    ����fusion_layer����һ��gru�����������self-attention��self_attentionҲ����Ӧ�ı�
            ���ģ�ȥ��gru,Ŀǰ�ṹΪ��filter(different from v11), gru, agg, gru, struc, max/mean pooling  dot, global(��С¹�����ϣ�0.83��
													  general,global����С¹�����ϣ�Ч�����ã�
													  dot, global����С¹������������,0.83��
            ��LSTMҲ�ӽ�ȥ����û�в���filter, lstm, agg, lstm, struc, max/mean pooling  dot, global��С¹����

pytorch_v13 ����v12�������һ����и��ģ���ʱ����structured_attention������tensorflow_v7
            ���ģ��ṹ��filter(from v11),gru, agg, gru, struc, max/mean pooling, dot, global(��С¹�����ϣ�0.83��
                                                                                 general,global����С¹�����ϣ�δ���ԣ���֪��Ч���������ܣ�
										 dot, global����С¹������������,0.83��
            ��GRU��ΪLSTM��filter,lstm,agg,lstm,struc,max/maen pooling  dot, global��С¹����

pytorch_v14 ����v11����aggregation_layer�����޸ģ��ο��ʼ�(�ʼ��ϵĻ�û��ʵ�֣���ʱ����cosine����)��
            ��ʵ���ҵ������ܣ�Ч�����ƻ���0.83�����Ա��ˣ���С¹��������0.83

pytorch_v15 ����v11����aggregation_layer�����޸ģ��ο��ʼǣ��ڱʼǱ����ܣ��Ƚ�����Ч��Ҳһ�㣬����ͣ��
            ׼����С¹�������ܣ���û��

pytroch_v16 ��aggregation��regional attention ���и��ģ�ʹ���������δ��ɣ�����ɣ���δ���У�

pytorch_v17 ͬ����aggregation���д�����attention���ֽ��д������ �����֮���attention���Լ� ������Ӽ��attention

pytorch_v_test ����v4�޸Ĵ��룬��Ҫ��ʵ��global attention��local attention

tensorflow_v3 
����pytorch��������ĵ�tensorflow�汾