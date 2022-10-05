## Resource Allocation for Cloud-Based Software Services Using Prediction-Enabled Feedback Control With Reinforcement Learning

### Summary

With time-varying workloads and service requests, cloud-based software services necessitate adaptive resource allocation for guaranteeing Quality-of-Service (QoS) and reducing resource costs. However, due to the ever-changing system states, resource allocation for cloud-based software services faces huge challenges in dynamics and complexity. The traditional approaches mostly rely on expert knowledge or numerous iterations, which might lead to weak adaptiveness and extra costs. Moreover, existing RL-based methods target the environment with the fixed workload, and thus they are unable to effectively fit in the real-world scenarios with variable workloads. To address these important challenges, we propose a Prediction-enabled feedback Control with Reinforcement learning based resource Allocation (PCRA) method. First, a novel Q-value prediction model is designed to predict the values of management operations (by Q-values) at different system states. The model uses multiple prediction learners for making accurate Q-value prediction by integrating the Q-learning algorithm. Next, the objective resource allocation plans can be found by using a new feedback-control based decision-making algorithm. Using the RUBiS benchmark, simulation results demonstrate that the PCRA chooses the management operations of resource allocation with 93.7 percent correctness. Moreover, the PCRA achieves optimal/near-optimal performance, and it outperforms the classic ML-based and rule based methods by 5\~7% and 10\~13%, respectively.

### Introduction

There are classic approaches (e.g., rule-based strategies [5], heuristics [6], and control theory [7]) that can solve the resource allocation problem to some extent. But most of them are unable to effectively meet the real-world requirements of software services in the cloud environment with dynamic workloads and service requests.

For instance, a fixed number of cloud resources can be easily allocated to software services by using rule-based strategies for meeting the expected maximum workload. However, it is difficult to set a resource threshold that can adaptively fulfill the dynamic demands of software services. Thus, they might lead to serious resource wastes. Moreover, heuristics commonly use the expert knowledge or management rules for a specific cloud system. Thus, they limit the application scopes and result in high overheads of rule settings and management.

Besides, the control-theory based methods require numerous iterations to find feasible resource allocation plans. Therefore, they may cause unnecessary costs due to the frequent switching of virtual machines (VMs). Besides, machine learning (ML) [8] or deep learning (DL) [9] based solutions commonly need a large amount of historical system data and massive training time to build accurate QoS or workload prediction models. However, there is commonly no sufficient training data in the real-world cloud environment. Thus, the accuracy of prediction models would be seriously affected, and it is difficult to support the effectiveness of resource allocation.

By contrast, reinforcement learning (RL) [10] can automatically make decisions through interacting with the environment without the support of historical data. Thus, RL has been recently used to tackle the complicated problem of resource allocation with low complexity and high robustness. However, the existing RL based methods target the environment with the static workload, and thus the decision-making model needs to be retrained when workloads change [11]. Therefore, these classic approaches are unable to efficiently adapt to the real-world scenarios of cloud-based software services with variable workloads and service requests.

To address these essential challenges, a Prediction enabled feedback Control with Reinforcement learning based resource Allocation (PCRA) method is proposed, in order to effectively achieve adaptive and efficient resource allocation for cloud-based software services. Through integrating the Q-learning algorithm [10] and multiple ML-based prediction learners, the proposed Q-value prediction model enables feedback control to efficiently find objective resource allocation plans for software services in the complex and dynamic cloud environment.

The main contributions of this paper are summarized as follows.

A new framework of resource allocation is designed to coordinate cloud resources for software services and collect runtime information. Based on the proposed framework, cloud resources are well monitored, while the decisions for resource allocation can be accurately made and executed.

First, the Q-learning algorithm is used to evaluate the values of management operations in terms of Q-values. Next, based on the Q-values calculated by the Q-learning, a Q-value prediction model is developed to offer accurate and adaptive prediction for the Q-values of management operations at different system states. Notably, the proposed Qvalue prediction model integrates multiple ML-based prediction learners, and the learner with the highest prediction accuracy is selected. Finally, a new feedback-control based decision-making algorithm is designed to make decisions for management operations based on the predicted Q-values, and it can be used to find objective resource allocation plans for cloud-based software services.

Extensive simulation experiments using the realworld RUBiS benchmark are conducted to validate the effectiveness of the proposed PCRA method in achieving adaptive and efficient resource allocation for cloud-based software services. The simulation results show that the PCRA method is able to choose management operations of resource allocation with 93.7 percent correctness. Moreover, the optimal/ near-optimal performance (QoS and resource costs) is obtained by using the PCRA method, and it outperforms classic ML-based and rule-based approaches by 5\~7% and 10\~13% under the runtime environment with various workloads and service requests.

The rest of this paper is organized as follows. In Section 2, the related work is analyzed. Section 3 formulates the resource allocation problem for cloud-based software services. In Section 4, the PCRA method is discussed in detail. Section 5 shows performance evaluation and analysis with the RUBiS benchmark. Finally, we conclude this work in Section 6.

### Related Work

...

The Johnson’s rule and the genetic algorithm were integrated in [14] for dealing with the problem of multiprocessor scheduling in cloud data centers.

...

An MLbased prediction model was designed in [26] to forecast the memory requirements of applications with specific service level agreements (SLAs).

...

### Problem Formulation

In this section, the problem of resource allocation for cloudbased software services is formulated. In general, self-adaptive cloud platforms are expected to balance QoS and resource costs when allocating resources to cloud-based software services. Thus, an objective function is needed to measure the potential resource allocation plans [34].

...

### Experiment

In this section, we first present the settings and datasets in our experiments (Section 5.1). Next, we implement the proposed PCRA method and conduct performance evaluation to explore the research questions (RQs) as follows.

    RQ 1: Whether the PCRA method is able to effectively realize adaptive resource allocation in different runtime environments (Section 5.2)?

    RQ 2: How does the PCRA method perform in Q-value prediction and decisions for management operations (Section 5.3)?

    RQ 3: How much does the PCRA method improve the performance of resource allocation compared with classic approaches (Section 5.4)?

For RQ 1, the experimental results show that the PCRA method achieves the performance comparable with the ideal resource allocation plans at different system states, and the performance gap between them is less than 3 percent. For RQ 2, the PCRA method can choose management operations of resource allocation with 93.7 percent correctness when using the SVM algorithm for training the Q-value prediction model. For RQ 3, the results show that the PCRA method outperforms the classic ML-based and rule-based resource allocation approaches by 5\~7% and 10\~13%, respectively.

