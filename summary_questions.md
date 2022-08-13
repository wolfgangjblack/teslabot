## Interview Readiness

1. What is the definition of a serverless application?

 - Serverless architecture is an approach to software design that allows developers to build and run services without having to manage the underlying infrastructure. Developers can write and deploy code, while a cloud provider provisions servers to run their applications, databases, and storage systems at any scale.

2. What is the definition of model serving and what are the two types?

 - Model serving is hosting machine-learning models to mkae their functions available via API so that applications can incorporate the models into their systems. 

 - the two types are Batch: which means we feed the model for model inference in a scheduled job, typically with a large amount of data and write the output to a table. The second type is Online, which menas the model is deployed with an endpoint so applications can send a request to the model and get a fast response at low latency.

3. What are 3 advantages of deploying using Model Serving methods Vs. deploying on GitHub Pages or HuggingFace for free?

 - Github Pages seems to be very complicated whereas AWS and Azure host several tutorial videos and how to use their products
 - Hugingface and GitHub free services have limits on inference and memory
 - The free services may not necessarily gaurantee static ips or constant service, paid services had better settings and controls for online applications

4. What is Machine Learning inference? How does this work? Give an example

 - What is Machine Learning Inference: The process of runnong data points into a ML model to calculate an output. Can also be thought of a predictions

 - this works by loading data for a prediction (or multiple in case of batch), doing any necessary data preprocessing needed to get the inference data in the form necessary for the model, then using a .predict() method to pass the data into the model and have the model output a label (in the case of classification) or a score to be used. 

Ex:
   - A DS gathers features and builds some model
   - model is taken by MLE, maybe some additional testing is done on model
   - model is deployed along with data pipeline
      - if batch, pipeline is scheduled as a job which reads in new data and generates a prediction and outputs in some table for later use
      - if online, an endpoint is connected to the model via an API and the model can be queried live for a prediction. If a large number of predictions are expected at the same time, traffic management should be considered. Even in this case, data is still saved for monitoring and historical records. 
