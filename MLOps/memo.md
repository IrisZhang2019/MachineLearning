# Introduction to Machine Learning in Production
memo for [course](https://www.coursera.org/learn/introduction-to-machine-learning-in-production/home/welcome) on Coursera

### Week 1: Overview of the ML Lifecycle and Deployment

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

### Week 2: Select and Train a Model

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

###### Data augmentation
create realistic examples that (i) algorithm does poorly on but (ii) humans (or other baseline) do well on.  
Checklist:
- does it sound realistic
- is the x -> y mapping clear
- is the algorithm currently doing poorly on it

###### Experiment tracking
Parameters to track
- algorithm/code vers.
- dataset
- hyperparameters
- results

Tools for tracking
- text files
- spreadsheet
- tracking system

Desirable features
- info needed to replicate results
- results with summary metrics/analysis
- perhaps also: resource monitoring, visualization, model error analysis

### Week 3: Data Definition and Baseline

###### Structured data vs. unstructured data
Structured data
- may be more difficult to obtain more data
- human labeling may not be possible

Unstructured data
- may or may not have huge collection of unlabeled example x
- human can label more data
- data augmentation more likely to be helpful

###### Small data vs. big data
Small data
- clean labels are critical
- can manually look through dataset and fix labels
- can get all labelers to talk to each other

Big data
- emphasis data process
- get to consistent definition with a small group, then send labeling instructions to labelers
- can consider having multiple labelers label ever example and using voting or consensus labels to increase accuracy

###### Label
can have a class/label to capture uncertainty, eg: unintelligible

###### HLP
uses
- in academia, support publication
- in business, establish a more reasonable target, then to prove ML system is superior

attention
- when ground truth is externally defined, HLP gives an estimate for Bayes/inrreducible error
- but ground truth is often just another human label

###### Pipeline
- keep track of data provenance (where it comes from) and lineage (sequence of steps)
- keep record of meta data if possible (meta data: the data of data)

###### Scoping
Feasibility: use external benchmark
- HLP
- is predictive features available/can get new predictive features?
- history of project: decrease of error comparing with HLP during project

Diligence on value
- ML engineering metrics vs Business metrics
