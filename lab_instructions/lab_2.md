# Create and Deploy a Form Recognizer Custom Model

### Overview
In this lab, you will create (train) an Azure Form Recognizer custom model using a sample training dataset. Custom models extract and analyze distinct data and use cases from forms and documents specific to your business. To create a custom model, you label a dataset of documents with the values you want extracted and train the model on the labeled dataset. You only need five examples of the same form or document type to get started. For this lab, you will use the dataset provided at [Custom Model Sample Files](/SampleInvoices/Custom%20Model%20Sample).


### Goal
* Use a sample training data set to train a custom model in the Azure Form Recognizer Studio
* Label the training data documents with custom fields of interest 
* Test the trained model on test data, visualized results and confidence score in the Studio
* Use the custom model in the BPA pipeline from Lab 1 


### Pre-requisites
* The accelerator is deployed and ready in the resource group
* You have an Azure subscription and permission to create a Form Recognizer Resource
* You have access to sample invoices folder with the invoices to upload


### Instructions

#### Create a Custom Model  
- [Step 1 - Open Form Recognizer Resource](#step-1---Open-Form-Recognizer-Resource)  
- [Step 2 - Open Form Recognizer Studio and Create a Custom Labeling Project ](#step-2---open-form-recognizer-studio-and-create-a-custom-labeling-project)  
- [Step 3 - Import the Sample Data](#step-3---import-the-sample-data)  
- [Step 4 - Train the model](#step-4---train-the-model)  
- [Step 5 - Test the Model on Test Data](#step-5---test-the-model-on-test-data)   

#### Step 1 - Open Form Recognizer Resource  

- From the Azure portal, click on **Resource groups** from the Navigate panel to see the resource groups.

   ![resourcegroup.png](https://github.com/shivashant25/sdp-workshop/blob/main/lab_instructions/images/bpas1.jpg?raw=true)  
   
- Click on the **business-process** resource group that is created for this lab, you should be able to see resources deployed as a part of Business Process Automation accelerator deployment.
    
   > **Note :** The names will be different in your specific labs and will not exactly match with the names of the resources or resource group

   ![resourcegroup.png](https://github.com/shivashant25/sdp-workshop/blob/main/lab_instructions/images/bpas5.jpg?raw=true) 
   
- Select the **Cognitive service accpunt** of type **Cognitive services multi-service account** which you'll be using in this lab. 

   ![resourcegroup.png](https://github.com/shivashant25/sdp-workshop/blob/main/lab_instructions/images/bpas8.jpg?raw=true)
   
- From the overview page, scroll down a bit and select **Form Recognizer**.

   ![resourcegroup.png](https://github.com/shivashant25/sdp-workshop/blob/main/lab_instructions/images/bpas9.jpg?raw=true)
   
- From the Form Recognizer tab, Click on **Go to Studio** button to navigate to **Form Recognizer studio**.

   ![resourcegroup.png](https://github.com/shivashant25/sdp-workshop/blob/main/lab_instructions/images/bpas10.jpg?raw=true)
   
   >**Note**: If the Login prompt pops-up, use the same credentials mentioned in the Environment details tab   

#### Step 2 - Open Form Recognizer Studio and Create a Custom Labeling Project 
 
![](images/step2b-Create-custom-labeling-project.png)  

- Create Custom Model Project  

![](images/step2c-Create-custom-labeling-project.png)  
![](images/step2d-Create-custom-labeling-project.png)  

- Provide the storage account and container containing the forms data which you will like to label  

![](images/step2e-Create-custom-labeling-project.png)  
![](images/step2f-Create-custom-labeling-project.png)  
![](images/step2g-Create-custom-labeling-project.png)  

#### Step 3 - Import the Sample Data  

![](images/step3a-import-sample-data.png)  
![](images/step3b-import-sample-data.png)  

- Create a new field which you would like to label  

![](images/step3c-import-sample-data.png)  

- We created the label as "Organziation_sample"  

![](images/step3d-import-sample-data.png)  

- Apply the custom label to form fields  

![](images/step3e-import-sample-data.png)  
- Apply the labels to all forms by repeating the process in step e  

![](images/step3f-import-sample-data.png)  

#### Step 4 - Train the model 

- After labeling the forms, click on "Train" and provide the below information
![](images/step4a-train-the-model.png)  

![](images/step4b-train-the-model.png)  

#### Step 5 - Test the Model on Test Data

![](images/step5a-test-the-model.png)  

![](images/step5b-test-the-model.png)  
- Load the test file and click "Analyze"  

![](images/step5c-test-the-model.png)  

- The results are projected with the confidence score  

![](images/step5d-test-the-model.png)  


#### Build new pipeline with custom model module in BPA  

- After you are sastified with the custom model performance, you can retrieve the model ID and use it in a new BPA pipeline with the Cusom Model module.

- Please repeat the steps in [Lab 1](/lab_instructions/lab_1.md) to create the following pipeline:
![](images/step6a-deploy-custom-model.png) 

![](images/step6b-deploy-custom-model.png) 

![](images/step6c-deploy-custom-model.png) 

- Retrieve the trained custom model ID from the Form Recognizer Studio and Enter it into the following window:
![](images/step6d-deploy-custom-model.png) 

![](images/step6e-deploy-custom-model.png) 

- Run the pipeline and visualize results in CosmosDB and search service as detailed in [Lab 1](/lab_instructions/lab_1.md).
![](images/step6f-deploy-custom-model.png) 

![](images/step6g-deploy-custom-model.png) 

## More Resources  

Getting Started with Form Recognizer Studio - https://learn.microsoft.com/en-us/azure/applied-ai-services/form-recognizer/form-recognizer-studio-overview?view=form-recog-3.0.0  

Form Recognizer Documentation - https://learn.microsoft.com/en-us/azure/applied-ai-services/form-recognizer/concept-invoice?view=form-recog-3.0.0
