# Title: Deployment of Supervised Learning Models for Predicting Chemical Toxicity Based on SMILES

Objective: To predict the toxicity of a chemical using simplified molecular input line entry system (SMILES) and deployed supervised learning models.

Approach: The predictions for the testing dataset in the Submission.csv file can be achieved in the following three ways:

1. Docker.
2. Run Toxicity-Prediction.ipynb with pre-generated features and predict the toxicity.
3. Run Toxicity-Prediction.ipynb to generate features and predict the toxicity.

This approach can help to accurately predict the toxicity of chemicals and ensure safety in various industries.


# Option 1: Dcoker

**Prerequisties:** 
To run the program with Docker, Docker Daemon should be running on your local machine. You can download and install Docker on multiple platforms. Refer to the below link and choose the best installation path for you:

Link to install Docker: https://docs.docker.com/get-docker/

**Note:** 
To reduce the runtime of the container, pre-generated features are used for the Docker image creation.

### Step1: 
Pull and run the Docker image from the Docker repository using the following command:

```bash
docker run devops333/toxicity-prediction:latest
```

### Step2: 
After running the Docker image, an instance of the container will be created. You can monitor the progress of the container by viewing the logs. Once the container has finished running, the predicted toxicity values will be saved to the output CSV file:

![image](https://user-images.githubusercontent.com/51771508/230697796-eda2511a-a1a6-4b3a-850f-f67bedf70ded.png)

### Step3:
Now run the below command to see the ContainerID and copy the ContainerID:
```bash
docker ps
```
![image](https://user-images.githubusercontent.com/51771508/230697879-a6c10d2a-cb38-4d7b-970a-576bb3460272.png)

### Step4:
Commit the Container with the ContainerID and copy the sha256ID as below:
```bash
docker commit ContainerID
```
![image](https://user-images.githubusercontent.com/51771508/230697984-308b8cdd-76b4-410e-85ab-64becc8acd54.png)

### Step5:
Run the below command with the sha256ID:
```bash
docker run -it sha256ID  bash
```
![image](https://user-images.githubusercontent.com/51771508/230698091-a61a8662-465e-4904-a97f-ac974b9ead3a.png)

### Step6: 
Now, open a new terminal and run the below command to copy the latest ContainerID:
```bash
docker ps
```
![image](https://user-images.githubusercontent.com/51771508/230699022-a263182c-298a-49a0-92b7-829efd9f9fba.png)
 
### Step7: 
Run the below command with the latest ContainerID and replace Your-Location with the choice of you local host machine location to store Submission.csv file:
```bash
docker cp latest-ContainerID:/app/Submission.csv Your-Location
```
![image](https://user-images.githubusercontent.com/51771508/230699060-6d32431d-4d62-4ce0-9b6b-331cc2958ef2.png)

**Docker Repository:**
The Docker image can be found in the following Docker Repository link: https://hub.docker.com/r/devops333/toxicity-prediction






## Prerequisties both for Option 2 and 3:

To run the IPython notebook files (*.ipynb), you will need to have Python3 and Jupyter Notebook installed on your computer. Follow the instructions below to ensure that you have the necessary prerequisites installed on your machine.

### 1. Installing Python3
Python3 is a programming language that is required to run the IPython notebook files. If you don't have Python3 installed on your computer, you can download it from the official website: https://www.python.org/downloads/.

### 2. Installing Jupyter Notebook

Jupyter Notebook is a web application that allows you to create and share documents that contain live code, equations, visualizations, and narrative text. To install Jupyter Notebook, follow the instructions below:

2.a) Go to the official Jupyter website: https://jupyter.org/install

2.b) Scroll down to the "Install Jupyter Notebook" section and select your operating system.

2.c) Follow the installation instructions for your operating system.


### 3. Required Libraries

To run this program on your local machine, you will need to install the following libraries using the command below:

```bash
pip install lightgbm numpy pandas sklearn rdkit tqdm boruta
```




# Option 2: Run Toxicity-Prediction.ipynb with pre-generated features and predict the toxicity.

### Step 1: 
Run **Section 1: Import Libraries**, to import the necessary libraries that are required for the program.

### Step 2:
Run **Section 3: Load the Generated Features**, with the train_400.csv and test_400.csv files that is presented in the GitHub repository.

### Step 3: 
Run **Section 5: Load the Pickle Files**, with the rfe_features.pkl and boruta_features.pkl files.

### Step 4:
Run **Section 6: Modelling**

### Step 5:
Run **Section 7: Result**, to generate the Submission file.




# Option 3: Run Toxicity-Prediction.ipynb to generate features and predict the toxicity.

### Step 1: 
Make sure Toxicity-Prediction.ipynb, train_II and test_II are in the same folder.

### Step 2:
Run all cells in the Jupyter Notebook file to run all of the cells and generate the Submission.csv file.


