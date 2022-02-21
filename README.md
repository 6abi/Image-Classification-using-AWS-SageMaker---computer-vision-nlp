# Image Classification using AWS SageMaker

Use AWS Sagemaker to train a pretrained model that can perform image classification by using the Sagemaker profiling, debugger, hyperparameter tuning and other good ML engineering practices. This can be done on either the provided dog breed classication data set or one of your choice.

## Project Set Up and Installation
Enter AWS through the gateway in the course and open SageMaker Studio. 
Download the starter files.
Download/Make the dataset available. 

## Dataset
The provided dataset is the dogbreed classification dataset which can be found in the classroom.
The project is designed to be dataset independent so if there is a dataset that is more interesting or relevant to your work, you are welcome to use it to complete the project.
![dataset](https://github.com/6abi/Image-Classification-using-AWS-SageMaker---computer-vision-nlp/blob/main/prints/dataset.png)

### Access
Upload the data to an S3 bucket through the AWS Gateway so that SageMaker has access to the data. 

## Hyperparameter Tuning
ResNet50 Model:

* This project uses the ResNet-18 pre-trained model.
* The ResNet-50 is a convolutional neural network that is 18 layers deep. This pre-trained version of the network is trained on more than a million images from the ImageNet database The pretrained network can classify images into 1000 object categories, such as keyboard, mouse, pencil, and many animals.
* The dataset that we are going to use are an Image dataset which consist of images of dogs.
* The dataset is divided into three parts training and validation and testing.
For hyperparameters, I tuned the two following ones :

Learning rate : -> default is 0.001 and the chosen range is =[0.0001, 0.1] -> learning rate is a ContinuousParameter.
epochs: -> defaut is 1e-08 and the chosen range is= [1e-9, 1e-8] -> the epochs is a IntegerParameter
Weight decay: -> default is 0.01 and the chosen range is = [1e-3, 1e-1]
Batch size : -> The chosen range is = [ 64, 128] -> batch-size is a CategoricalParameter
Remember that your README should:
- Include a screenshot of completed training jobs
- ![jobs](https://github.com/6abi/Image-Classification-using-AWS-SageMaker---computer-vision-nlp/blob/main/prints/jobs.PNG)
- Logs metrics during the training process
- ![log_metric](https://github.com/6abi/Image-Classification-using-AWS-SageMaker---computer-vision-nlp/blob/main/prints/log_training.PNG)
- Tune at least two hyperparameters
- ![turning](https://github.com/6abi/Image-Classification-using-AWS-SageMaker---computer-vision-nlp/blob/main/prints/training_job.PNG)
- Retrieve the best best hyperparameters from all your training jobs
- ![best_hyper](https://github.com/6abi/Image-Classification-using-AWS-SageMaker---computer-vision-nlp/blob/main/prints/hyperparameters.PNG)
## Debugging and Profiling
 - Debugging and Profiling was done with the help of the sagemaker.debugger module.
 - Amazon SageMaker Debugger provides full visibility into training jobs of state-of-the-art machine learning models.
 - This SageMaker Debugger module provides high-level methods to set up Debugger configurations to monitor, profile, and debug your training job.
 - Configure the Debugger-specific parameters when constructing a SageMaker estimator to gain visibility and insights into your training job.

### Results
- ![result](https://github.com/6abi/Image-Classification-using-AWS-SageMaker---computer-vision-nlp/blob/main/prints/result.png)
The training output had a linear decay without oscillations.
TODO: If not, suppose there was an error. What would that error look like and how would you have fixed it? Making some adjustments in the pretrained model to use a different set of the fully connected layers network.

- ![result - test model](https://github.com/6abi/Image-Classification-using-AWS-SageMaker---computer-vision-nlp/blob/main/prints/result_2.PNG)
## Model Deployment
**TODO**: Give an overview of the deployed model and instructions on how to query the endpoint with a sample input.
Model was deplyed in "ml.g4dn.xlarge" instance and were queried with images as input to the endpoint created as a result of model deployment. The Endpoint was storeged in S3 object after deployment.

**TODO** Remember to provide a screenshot of the deployed active endpoint in Sagemaker.
- ![endpoint](https://github.com/6abi/Image-Classification-using-AWS-SageMaker---computer-vision-nlp/blob/main/prints/endpoint.PNG)
## Standout Suggestions
**TODO (Optional):** This is where you can provide information about any standout suggestions that you have attempted.
