
# External Links

Moved
https://www.notion.so/CVSD-Interview-41030b0ba968428b8e9d1e012830b4eb

Plan
https://github.com/alirezadir/Machine-Learning-Interviews/blob/main/src/MLSD/ml-system-design.md

AI Design Interview Questions
https://chatgpt.com/c/59634084-41b8-412c-89c1-e7613ac38dec

# Topics

questions
- Bird’s-Eye-View Transform


# Overview

Common
- FPN
    - feature maps at multiple resolutions within the network
- Video
    - temporal information from video
    - temporally consistent global 3D human pose
        - VNect
	- tracking

Deep dive
- [[Edge Device Inference]]
- DINO
- SAM


# Plan


## Step 1. Requirements

Problem Exploration
Problem Formulation

Business
- Business goal
- Define business metric
    - Examples
    - [[Metrics]]

Scope
- Functional requirements
- User actions
- Natural labels

Design Objectives
- Non-functional requirements.
- Accuracy
    - What is most important precision or recall ?
    - See Metrics
- Performance
    - real-time performance
    - 30 fps → 1000 / 30 = 30 ms
- Platform
    - Edge device
    - Cloud
- Usability
- Scalability
    - only for Cloud?

Optimization Goals
- Overview
    - Really important for Edge
    - Also good to consider for cloud
- Edge
    - Energy Efficiency
    - Binary size
- Minimizing Latency
    - Real-time performance
- Maximizing Throughput
    - Cloud

Tradeoffs
- Accuracy vs. Performance


## Step 2. Define ML/CV problem


Translate an abstract problem into an ML/CV problem

DL vs. CV
- see below

X and Y
- Target for learning


## Step 3. Evaluation and metrics


Metrics
- Offline metrics
    - Imbalanced data
- Non-Functional
    - Latency
    - Inference time
- Online metrics
    - Task/session success/failure rate
    - Engagement rate (like rate, comment rate)
    - Direct negative feedback (hide, report)
- Proxy metrics

Questions
- What is most important FP or FN ?
- What is most important precision or recall ?

Evaluation
- train / val / test splits
- avoid data leaks

## Step 4. Data handling

Summary
- Not for ML only, traditional CV also needs data at least for evaluation.
- Data for training and evaluation

Data sample
- X and Y

What data do we need
- Do we need fresh data?
	- see below

What data do we have
- Open source datasets
- Annotated data
- Raw data
- Human annotation (super costly, slow, privacy issues)
- You need to remember existing datasets!

When we have small data
- Synthetic data
- Active Learning
- Pseudo Labeling
- SSL
    - Contrastive learning
- SAM and DINO
    - Which pretrain is better SAM or DINO?
	- [[SAM]]
	- [[Human-in-the-Loop (HITL)]] ?
- Transfer learning
- Weak supervision

Advanced
- teacher-student
- data-engine
- foundation models
- VLM
    - cheap data for pre-train

Data balancing
- [[Class Imbalance]]
- Imbalanced data
- loss
- sampling

Training optimization
- cs231n
- pre-process
- dump features to disk

Feature Engineering
- CV?

## Step 5. Main components

Main components
- MVP
- Model
- Loss

High level architecture and main components
- do we need?

Baseline
- 3rd party solution
- complexities on the border of the system
- foundation models

Model
- Method we will use to solve the problem
- You spent most of the time to prepare for this section?
- Bias-Variance Tradeoff
- DL vs. CV

Model selection
- Heuristics
    - CV?
- Simple model
    - SimpleBaseline, SimpleBaseline3D
    - top-down
- More complex model
    - e2e
    - bottom-up

DL vs. CV
- ML-based approaches
- Classical CV approaches
- Trade-offs
    - Know trade-offs between Classical CV and ML-based approaches for each case.

Traditional CV
- Pros
    - performance
    - easier integration
- Cons
    - robustness
    - complex environments
    - reflective surfaces

Pipelines
- adding new data
- data storadge
- model registry
- preparation for handy iteration process

How many data we need to train the model?
- For example transformer architecture can require more data for training than CNN. We can explain it in the following way: CNN has strong inductive bias for image task which transformers do not have.

How many time we need to train the model?
- Several hours good
- [[TNN. Training Speed.]]

How many hardware we have?
- A100, V100

Training
- Training Optimization
- finetune
- train from scratch
- transfer learning
- augs
    - CutMix
    - Mosaic

Which distribution target have?
- CV?

Interpretation of the model
- CV?

Offline evaluation
- Step 3. Evaluation and metrics

Distributed training
- CV?

Probabilities
- calibration
- needed if we want to compute expectation


## Step 6. Deploynment


Edge
- [[Edge Device Inference]]
- Computational capacity on target devices
    - BOTEC
    - BOTEC here or it should be earlier?
- CPU vs. GPU

Important moments
- Efficient algorithms
- Monitoring
	- [[Monitoring]]
    - Device models
    - Statistics of user's device models

Edge optimization
- Fusing of layers
- Using layers that supported by the platform/GPU/ANE
- Model compression
- Arch
    - depth-wise convolutions
    - inverted residual modules
        - TBD
    - MobileNet
- Inspect layers manually
    - Feature maps and size of target object

Model compression
- Quantization
    - do not quantize the first conv layer
- Distillation
    - teacher-student

Service
- [[Prediction Modes]]
- batch mode
- online mode

Infrastructure
- Infrastructure for training
- Inexpensive on-demand compute resources
    - AWS
    - Google
    - What Meta uses?

Continual learning
- [[Continual Learning]]
- Do we need fresh data?
	- Make an experiment, sequentially training your model on historical data.

Network
- Run strong model in the cloud
- Network connection
    - BOTEC bandwidth
- Examples
	- SAM
	- Translator App

## Step 7. Monitoring and online evaluation

[[Monitoring]]

Online evaluation
- [[Test in Production]]
- [[AB Tests]]
	- metric
	- null hypothesis
	- p-value


What to monitor
- Bug in model
- Online metric
- New data?
    - Getting new data from user?
- Device models
- Statistics of user's device models

Data
- User privacy
- Requesting data from users


## Step 8. Scaling


Distributed training

TODO


# Systems

