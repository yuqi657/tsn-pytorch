<!--
 * @Author: your name
 * @Date: 2021-04-15 19:04:35
 * @LastEditTime: 2021-06-11 17:09:27
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /tsn-pytorch/README.md
-->
# TSATM  

本文提出了细粒度动作识别数据集“StreetDance”，包含245种细粒度街舞动作类别，7,095个视频片段。本文的街舞数据来自于综艺、教程，有着自带的注解，本文采用OCR技术识别这些注解，进行半监督的视频标注，在保证专业性的同时，降低了标注成本。据调研，“StreetDance”数据集是专注于街舞领域的首个细粒度数据集，时序信息丰富，有着层次化的标签。该数据集能够支持一些有趣的任务，如街舞动作迁移学习、视频理解任务与艺术领域的结合等。  
在分类方法层面，如何让模型拥有较低的计算复杂度和较高的准确性是一个重大的挑战，2D CNN方法计算复杂性低但是无法捕捉时序信息，3D CNN方法性能好但是计算复杂度高。本文提出了TSATM模型，该模型在2D CNN模型的基础上，增加ATM模块，提高模型的性能。ATM模块由两部分组成：时序空间网络和动作特征提取网络。  
本文进行了大量的对比实验，探究动作识别的相关问题及TSATM模型的表现。由于本数据集分类粒度更加精细，更加注重身体姿势的变化，因此识别难度更高，实验表明，当前的一些动作识别模型在本文数据集的识别准确率不够高。TSATM模型通过建模时序空间信息和动作信息，在2D CNN方法中表现略有优势。希望本文提出的数据集和方法能够推动细粒度动作识别领域相关研究的发展。  

模型训练和测试如下：  
* Train: bash ./scripts/train_model.sh  
* Test: bash ./scripts/test_model.sh  


具体配置（如采样帧数）可在以上两个shell文件中进行更改
