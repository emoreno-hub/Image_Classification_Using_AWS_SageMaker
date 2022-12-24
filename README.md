# Image Classification using AWS SageMaker

Use AWS Sagemaker to train a pretrained model that can perform image classification by using the Sagemaker profiling, debugger, hyperparameter tuning and other good ML engineering practices. This can be done on either the provided dog breed classication data set or one of your choice.

## Project Set Up and Installation
Create an AWS account if you don't already have one and setup SageMaker Studio.
Download the starter files.
Download the dataset and store in an S3 bucket.

## Dataset
The provided dataset is the dogbreed classification dataset which can be found in the classroom.
The project is designed to be dataset independent so if there is a dataset that is more interesting or relevant to your work, you are welcome to use it to complete the project.

### Access
Upload the data to an S3 bucket through the AWS Gateway so that SageMaker has access to the data. 

## Hyperparameter Tuning
Hyperparameter tuning for the Resnet50 model was performed by searching across the following parameters:
- Learning Rate: `ContinuousParameter(0.001, 0.1)`
- Batch Size: `CategoricalParameter([64, 128])`
- Epochs: `IntegerParameter(2, 4)`

**Optimizer**
The Adam optimizer was used for training. The Adam optimization algorithm is an extension to stochastic gradient descent that has recently seen broader adoption for deep learning applications in computer vision and natural language processing.  

## Debugging and Profiling
The SageMaker Debugger was used for debugging by adding hooks to the train and test models and then registering the models along with registering the loss function.  SageMaker Profiler was used to check how well the model training was performing and to analyze the instance resource and GPU/CPU utilization.

### Results
(https://github.com/emoreno-hub/Image_Classification_Using_AWS_SageMaker/blob/main/screenshots/Debugging_and_Profiling.PNG)

The debugger output shows that there isn't any anomalous behavior but if there was, some steps to improve performance could be to try a different architecture for the CNN model along with using a wider range of hyperparameters.


The profiler can be viewed here: [Profiler Report] (https://github.com/emoreno-hub/Image_Classification_Using_AWS_SageMaker/blob/main/ProfilerReport/profiler-output/profiler-report.html)

## Model Deployment
**TODO**: Give an overview of the deployed model and instructions on how to query the endpoint with a sample input.

**TODO** Remember to provide a screenshot of the deployed active endpoint in Sagemaker.

## Standout Suggestions
**TODO (Optional):** This is where you can provide information about any standout suggestions that you have attempted.
