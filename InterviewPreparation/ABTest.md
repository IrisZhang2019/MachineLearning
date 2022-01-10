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
