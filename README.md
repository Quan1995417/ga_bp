# ga_bp
### a back propagation neural network with genetic algorithm

利用遗传算法对bp神经网络进行权值优化
优化过后，loss收敛速度变快，收敛结果较为稳定，结果较未优化的相比小了一点，这说明遗传算法有一定的作用。
但效果不是特别显著，均方误差0.001，是现在最好的情况，也勉强还可以接受，到时候再挣扎一下...

### .py说明
1. ga_main.py
>程序入口函数，定义ga一些参数，负责整体的ga_bp过程
2. ga_encoding.py
>ga编码函数，对所有的变量进行编码，这里采用的是二进制编码，实数编码准备在考虑一下
3. ga_decoding.py
>ga解码函数，对编码后的二进制码进行解码，转换成十进制形式
4. ga_calObject.py 
>计算目标值，是调用神经网络的函数
5. ga_calFitness.py
>计算每一代种群中的最优个体
6. ga_replace.py
>个体替换函数，用上一代最优个体替换本代最差个体
7. ga_selection.py
>ga选择函数，以轮盘赌的方式选择一些个体组成新的种群，淘汰掉一些目标值较低的个体
8. ga_crossover.py
>ga交叉函数，以一定概率选择两个个体进行交叉
9. ga_mutation.py
>ga变异函数，以一定概率选择个体进行变异
10. ga_getBest.py
>从所有代中选择一代最优种群
11. bp_object.py
>该函数位于ga_calObject.py中，用于计算loss，并返回loss的倒数作为目标值
12. bp_train.py
>遗传算法迭代结束后选择最优权值传入此文件中进行训练，达到优化效果
13. 10790.csv
>训练数据（打乱）