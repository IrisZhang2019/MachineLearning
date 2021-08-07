# Memo for [Introduction to Machine Learning in Production](https://www.coursera.org/learn/introduction-to-machine-learning-in-production/home/welcome)

#### Week 1: Overview of the ML Lifecycle and Deployment

###### Concept drift vs Data drift

concept drift: drift of mapping x -> y

data drift: drift of x

###### Software engineering issues
- Realtime or Batch
- Cloud vs Edge/Browser
- Compute resources (CPU/GPU/memory)
- Latency, throughput (QPS)
- Logging
- Security and privacy

###### Common deployment cases
- Gradual ramp up with monitoring
- Rollback

###### Ways of deployment
- Canary deployment: roll out to small fraction of traffic initially, monitor system and ramp up gradually
- Blue green deployment: Old/Blue version, New/Green version, easy to rollback

###### Metrics

Software metrics: memory, compute, latency, throughput, server load

Input metrics: avg input length, volume, # missing values, avg img brightness

Output metrics: # times return "", # times user redoes search, # times switched to typing, CTR

#### Week 2: Select and Train a Model

###### Performance on key slices of the dataset
eg loan approval: not to discriminate by ethnicity, gender, location, language or other protected attributes

###### Establish a baseline
- Human Level Performance (HLP)
- Literature search for state-of-the-art/open source
- Quick-and dirty implementation
- Performance of older system

###### Sanity check 健全性检查
Try to overfit a small training dataset before training a large one  
在小样本上检验learning algorithm 可不可用

###### Error Analysis
- what fraction of errors has that tag
- of all data with that tag what fraction is misclassified
- what fraction of all the data has that tag
- how much room for improvement is there on data with that tag

###### Prioritizing
- room for improvement
- frequency of the category
- how easy to improve it
- importance to improve it
