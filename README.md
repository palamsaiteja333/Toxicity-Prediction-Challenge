# Toxicity Prediction Challenge
Deployed Supervised Learning Models to predict the toxicity of a chemical based on SMILES (Simplified Molecular Input Line Entry System).

The Jupyter Notebook file Toxicity.ipynb can be run in the following two ways:

# Option 1: Run with Original Dataset Files

**Prerequisties** 
In order to run the this program in the Local Machine, the following libraries must be installed. 
The libraries can be installed in the Local Machine using the following command:

```bash
pip install networkx
```
```bash
pip install tf2_gnn
```
```bash
pip install tensorflow
```

### Step 1: 
Download and Extract the training and testing dataset file:

Download the **data.zip** file and extract it; on extracting the data.zip file, **train.sdf** can be found.

Place the **train.sdf** file in a folder of your choice.


### Step2:
Download the Python file:

Download the **predictting-the-efficiency-of-anti-cancer-drug.py** file into the same folder where the train.sdf file present.


### Step3:
Run the program:

If both the given dataset file (**train.sdf**) and python program (**predictting-the-efficiency-of-anti-cancer-drug.py**) are in the same folder then the python program can be executed without any changes to the program.

If the location of train.sdf dataset is in different folder then the location of the dataset should be given to the load method in the python program to read the data.



# Using Docker:

**Note:** 
In order to run the program with Docker, Docker Daemon should be running in your local machine.
You can download and install Docker on multiple platforms. Refer to the below link and choose the best installation path for you: 

Link to install Docker: https://docs.docker.com/get-docker/


### Step1: 
Pull the docker image from the Docker repository using the following command:

```bash
docker pull devops333/predicting_the_efficiency_of_anti_cancer_drug
```

### Step2:
Now run the image that is downloaded using the following command:

```bash
docker run devops333/predicting_the_efficiency_of_anti_cancer_drug
```

### Step3:
After Step2, a container will start running which is an instance of the image (**devops333/predicting_the_efficiency_of_anti_cancer_drug**) and when the run is finished, URL's are shown in the terminal informing to copy and paste one of these URL's to access the output.


**Docker Resource:**
The Docker image can be found in the following Docker Repository link: https://hub.docker.com/r/devops333/predicting_the_efficiency_of_anti_cancer_drug
