* 样本量？
* 实际cases？

#### Udacity A/B Testing
L3  
A/B test可以用作比较，但是不能提供新的option，另外对于一个和之前一点不相同的新feature也不适合比较。有时变化的feedback时间太长不适合做test.

L9 metrics  
CTR - Click Through Rate: number of clicks / number of page views  
某一个按键的usability

Click Through Probability: unique visitors who click/ unique visitors to page

选择A或者B～二项分布  
标准差=sqrt(p(1-p)/n)  
当np>=5时上述趋近于正态分布，可以用正态分布检验

null hypothesis 零假设 /alternative hypothesis 

L19 pooled standard error

第一类错误第二类错误  
第一类错误：原假设H0为真而拒绝原假设称为犯了第一类错误，alpha显著水平  
第二类错误：原假设H0为假但是接受了，beta (false negative)，sensitivity=1-beta，一般设定为80%  
小样本的话beta容易大，即试了几个都成立就觉得所有的可能都成立，然而实际不是这样的  

L23 
https://www.evanmiller.org/ab-testing/sample-size.html  
Baseline conversion rate: 正常情况下大CTR  
Minimum detectable effect: 判断变化多少的话算是有区别的阈值  
能算出需要多少个样本数

L26  
已知控制组和实验组的有多少浏览和点击，可以求出它们差别的平均值d和标准差SE，于是知道两组之间的差距～N(0, SE)  
即两组差距在d±1.96SE之间。  
决策需要知道的是上面的差距和Minimum detectable effect比是大是小进而决策  
如果d±1.96SE都在Minimum detectable effect之外那么决定采用实验组，如果都在之内则说明没有显著变化，如果有一部分重叠有一部分超出去了可能还需要多采集样本继续分析。
