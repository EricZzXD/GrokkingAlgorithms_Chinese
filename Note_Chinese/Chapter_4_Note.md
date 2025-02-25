# 算法图解笔记 -> 第四章: 快速排序

## 4.1 分而治之 -> P41
   - 文章中例子的解释（一小块土地，把他均匀地分成方块，且分出的方块要尽可能大）
       - 所以把土地最大的分成两份正方形，如何有剩下的， 再继续把他分成两份正方形。 
       - 直到分成两个正方形后没有剩下的空间。
       - 那么这个正方形就是在最初的那片土地，适用的最大正方块
   

   - D&C的工作原理：
       1. 找出简单的基线条件
       2. 确定如何说笑问题的规模，使其符合基线条件
   
   - D&C 并非可用于解决问题的算法，而是一种解决问题的思路。
   

   - 练习 -> P47
        - 4.1 请编写前述sum函数代码：
            - 查看 Chapter_4 -> Exercise4_1
                 
        - 4.2 编写一个递归函数来计算列表包含的元素数：
            - 查看 Chapter_4 -> Exercise4_2

        - 4.3 找出列表最大的数字：
            - 查看 Chapter_4 -> Exercise4_3
      
        - 4.4 还记得第1章介绍的二分查找吗？它也是一种分而治之算法。你能找出二分查找算法的基线条件和递归条件吗？
            - 查看 Chapter_4 -> Exercise4_4
      

## 4.2 快速排序 -> P47
   - 基本原则
       - 当数字为空或只包含一个元素，只需原样返回数组    ----- 不用排序
       - 当包含两个元素，只需要比大小去检查是否需要交换位置    ----- 两个元素的数组排序很简单
       - 当元素大于两位，使用D&C，因此需要将数组分解，直至满足基线条件。 
       
       （个人理解）
       - 简单来说，快排就是选取列表里面得一个数为对比值，分开小于对比值的和大于对比值的 (这就是所谓的分区)
       - 分区后再继续上一步骤直到排序完成。
       - 定义为排序完成 -> 列表为空的，或者只有一个元素
       
   - 原理
       - 从数组选择一个元素为基准值（pivot）
       - 找出比基准值小的元素和比基准值大的元素， 这被成为分区 （partitioning）
       - （到这一步骤，结束分区，得到的数组是无序的）
       - 然后分区之后再分别对两个分区进行快排，直到得到结果
    

## 4.3 大O表示法 -> P52
   - 算法大O对比
   
       | 算法  | 二分查找  | 简单查找  | 快速排序  | 选择排序  | 旅行商问题算法  |
       |---|---|---|---|---|---|
       | 数组长度 |   O(logn)  | O(n)  | O(n*logn)  | O(n^2)  | O(n!)  |
       | 10  | 0.3S  | 1s  | 3.3s  | 10s  |  4.2 Days |
       |  100 | 0.6S  | 10s  | 66.4s | 16.6 mins  | 2.9x10^149 Years  |
       |  1000 |  1s |  100s |  996s | 27.7 hrs  | 1.27 x 10^2559 Years  |
        


   - 练习 -> P56
        使用大O表示法时，下面各种操作都需要多长时间?
        - 4.5 打印数组中的各个元素值
            O(n) 
        - 4.6 将数组中每个元素的元素值都乘以2
            O(n)
        - 只将数组中第一个元素的值乘以2
            O(1)
        - 根据数组包含的元素创建一个乘法表，即如果数组为[2, 3, 7, 8, 10]，首先将每个元素 都乘以2，再将每个元素都乘以3，然后将每个元素都乘以7，以此类推。
            O(n^2)
   
## 总结
   - 4.4 小结
       - D&C将问题逐步分解，只用D&C处理表时，基线条件很可能时空数组或只包含一个元素的数组
       - 实现快速排序时，请水机的选择用作基准值的元素。快速排序的平均运行时间为O(nLogn)
       - 大O表示法中的厂里有时候事关重大，这就是快排比合并快的原因所在
       - 比较简单朝朝和二分法查找，常量几乎无关要紧，以为列表很长时，O(logn)的熟读比O(n)快得多
