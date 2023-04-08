# Title: Deployment of Supervised Learning Models for Predicting Chemical Toxicity Based on SMILES

Objective: To predict the toxicity of a chemical using simplified molecular input line entry system (SMILES).

Approach: The predictions for the testing dataset in the Submission.csv file can be achieved in the following three ways:

1. Docker.
2. Run Toxicity-Prediction.ipynb file with pre-generated features and predict the toxicity.
3. Run Toxicity-Prediction.ipynb file to generate features and predict the toxicity.

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
Now run the below command to copy the ContainerID of devops333/toxicity-prediction:latest image:
```bash
docker ps -a
```
![image](https://user-images.githubusercontent.com/51771508/230738024-d8b09bc4-7c6f-4899-bd3b-dc8c4a11df7c.png)

### Step4:
Commit the Container with the ContainerID and copy the sha256ID as below:
```bash
docker commit ContainerID
```
![image](https://user-images.githubusercontent.com/51771508/230738096-dec7f9cd-c50e-46ab-b84c-b668038f9dad.png)

### Step5:
Run the below command with the copied sha256ID:
```bash
docker run -it sha256ID  bash
```
![image](https://user-images.githubusercontent.com/51771508/230738192-e65dbeeb-cca9-40d6-84e9-103d3819784c.png)


### Step6: 
Now, open a new terminal and run the below command to copy the latest ContainerID:
```bash
docker ps
```
![image](https://user-images.githubusercontent.com/51771508/230738234-2e1c05d3-eaf1-4966-8559-0957f726fbb8.png)

 
### Step7: 
Run the below command with the latest ContainerID and replace Your-Location with the choice of you local host machine location to store Submission.csv file:
```bash
docker cp latest-ContainerID:/app/Submission.csv Your-Location
```
![image](https://user-images.githubusercontent.com/51771508/230738333-fcf12eaa-1139-40cc-b775-ca83dd26cec0.png)

### Step8:
Now, go to the above specified path to find the Submission.csv file.


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
pip install lightgbm numpy pandas sklearn rdkit tqdm boruta pickle
```




# Option 2: Run Toxicity-Prediction.ipynb file with pre-generated features and predict the toxicity.

### Step 1: 
To begin, you must download the entire repository from GitHub onto your local machine and extract it. Once extracted, you will notice another zip file named "400_features.7z" inside. Extract this file as well to obtain the "train_400.csv" and "test_400.csv" files.

After extracting all necessary files, place them into a single folder. In doing so, you will be able to successfully run the program. Below is a list of files you should have in the designated folder to ensure proper execution of the program.

```bash
Toxicity-Prediction.ipynb
train_400.csv
test_400.csv
test_II.csv
train_II.csv
boruta_features.pkl
rfe_features.pkl
```

### Step 2:
Run **Section-1: Import Libraries**, to import the necessary libraries that are required for the program.

### Step 3:
Run **Section-3: Load the Pre-Generated Features**, with the train_400.csv and test_400.csv files that is presented in the GitHub repository.

### Step 4: 
Run **Section-5: Load the Pre-Selected Features**, with the rfe_features.pkl and boruta_features.pkl files that is presented in the GitHub repository.

### Step 4:
Run **Section-6: Modeling**

### Step 5:
Run **Section-7: Result**, to generate the Submission file.




# Option 3: Run Toxicity-Prediction.ipynb file to generate features and predict the toxicity.

### Step 1: 
To begin, you must download the entire repository from GitHub onto your local machine and extract it. Once extracted, you will notice another zip file named "400_features.7z" inside. Extract this file as well to obtain the "train_400.csv" and "test_400.csv" files.

After extracting all necessary files, place them into a single folder. In doing so, you will be able to successfully run the program. Below is a list of files you should have in the designated folder to ensure proper execution of the program.

```bash
Toxicity-Prediction.ipynb
train_400.csv
test_400.csv
test_II.csv
train_II.csv
boruta_features.pkl
rfe_features.pkl
```

### Step 2:
To generate the "Submission.csv" file, simply run all cells within the Jupyter Notebook file. This will ensure that all cells are executed and the desired output is obtained.


