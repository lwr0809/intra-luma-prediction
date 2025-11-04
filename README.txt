1、代码平台版本：VVCSoftware_VTM-VTM-23.1
2、宏定义：
	SPLIT_SHOW为1时，开启色度块划分可视化
	SPLIT_SHOW和SPLIT_SHOW_LUMA为1时，开启亮度块划分可视化
###########################亮度预测###################################
	Test_Limit_Performance、New_Softmax和RDO_COST为1时，迭代寻找最优theta值信息，将theta写入码流，并使用率失真代价判断
	New_Softmax为1时，theta值设为-0.01，进行CU预测值的生成
                Copy_block为1时，按照对角线方向，最近邻Copy模式

	Template_theta为1时，基于当前CU的上方重建CU信息确定theta值，用于当前CU预测值的生成
	Copy_and_Planar为1时，最近邻Copy模式和最近邻模式，取加权平均
	Flip_Vertical为1时，按照45°对角线方向(即：负对角线方向)，最近邻Copy模式
	RDO_Flip_Vertical为1时，Copy_block方法和Flip_Vertical方法，两者通过率失真代价判断，选最优，但需要将是否翻转，写入码流

###########################色度预测###################################
	Template_theta_chroma为1时，基于当前CU的上方重建CU信息确定theta值，用于当前CU色度预测值的生成
	Softmax_chroma为1时，heta值设为-1，进行CU色度预测值的生成
				
	