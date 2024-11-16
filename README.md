
# Paris Olympic 2024 Data Analysis

## Dashboard Link: https://app.powerbi.com/view?r=eyJrIjoiMGYyN2ZlNmEtM2Q2NC00Yjk4LWFlYTktNGZmYzhjZThjZjUwIiwidCI6Ijk4YzJkMGYzLWRhYjctNDg1MS04MTA5LWJlYmUwNzdiYjU4NyIsImMiOjEwfQ%3D%3D

## Introduction
The Paris 2024 Summer Olympics are expected to be a spectacular event, and examining the associated datasets might give significant insights on many facets of the events. In this analysis, we will look at how to use Python to obtain and manage a dataset from Kaggle, followed by Power BI to show the insights for effective analysis.

## Step 1:
Setting Up Kaggle API and Python Environment
First, we need to set up the Kaggle API to access and download datasets. Follow these steps:

1. Sign up on Kaggle: If you don’t have a Kaggle account, sign up here.
2. Create an API Token: In your Kaggle account settings, go to the “API” section and click “Create New API Token.” This will download a kaggle.json file containing your credentials.
3. Save the API Token: Place the kaggle.json file in a secure directory on your machine, where it will be used to authenticate the Kaggle API.

## Step 2:
Python Script for Downloading the Dataset

![image](https://github.com/user-attachments/assets/cba14fa1-de9f-44e6-ac49-c864ca61debb)
![image](https://github.com/user-attachments/assets/a3dbc9ae-084e-426e-a36b-1b8767eb6e55)
![image](https://github.com/user-attachments/assets/f578c307-2d71-45b6-be57-fd90563a4e3b)
![image](https://github.com/user-attachments/assets/bc2960d9-fc36-479f-9bfa-f0f99269bcf2)

## Explanation of the code:
1. Kaggle API Setup and Configuration: 
import kaggle  
import os  
import pandas as pd 

These lines import the necessary libraries:   
a) kaggle to interact with the Kaggle API,  
b) os for file and directory manipulation   
c) pandas (abbreviated as pd) for handling data in table format. 

2. Setting Kaggle API Credentials:  
os.environ['KAGGLE_CONFIG_DIR'] = 'C:/directory/.kaggle'  

This line points to your Kaggle configuration file (which stores your API credentials) to enable 
the code to communicate with Kaggle and download data securely. 

3. Defining the Dataset and Download Path:  
dataset = 'piterfm/paris-2024-olympic-summer-games' 
download_path = 'C:/directory’  

a) The dataset variable specifies the Kaggle dataset identifier.  
b) download_path sets the directory where downloaded files will be saved, which you can 
adjust based on where you’d like the files.

4. Clearing the Download Directory:  
for file in os.listdir(download_path): 
file_path = os.path.join(download_path, file)  
if os.path.isfile(file_path): 
os.unlink(file_path)  # Delete the   

a) This part removes any files in download_path to avoid duplicates or conflicts with 
previously downloaded data.  
b)  It checks each item in the directory, and if it’s a file, it deletes it. 

5. Downloading the Dataset:  
kaggle.api.dataset_download_files(dataset, path=download_path, 
unzip=True)  

This line downloads and unzips the Kaggle dataset into the specified download folder.

6. Loading CSV Files into Pandas DataFrames:  
csv_files = [...]  
dataframes = {}  
for file in csv_files:  
file_path = os.path.join(download_path, file)  
df = pd.read_csv(file_path)  
table_name = file.split('.')[0]  
dataframes[table_name] = df  

a) csv_files is a list of all CSV files within the downloaded dataset.  
b) The loop iterates through each CSV file, reads it into a Pandas DataFrame, and stores it 
in a dictionary named dataframes. The keys in this dictionary are the file names (without 
the .csv extension), making it easier to reference individual tables later.

## Visual -1
The Title Page:
![image](https://github.com/user-attachments/assets/95cbb854-1f20-4928-a8b2-ec764831892b)

## Visual -2
Medals Highlights and Analysis:
![image](https://github.com/user-attachments/assets/bed5bee8-e823-4187-99b6-85c4a169de8b)

## Visual -3
Medalist Highlights and Analysis on Different Metrics:
![image](https://github.com/user-attachments/assets/1a0ece23-b507-4376-984c-5eb91fd54d74)

## Visual -4
Medal Count by Athletes: 
![image](https://github.com/user-attachments/assets/028d5856-9bd2-4dde-9cc0-dcb6d443eaaf)

## Visual -5
Medal Count by Countries and top performing countries:
![image](https://github.com/user-attachments/assets/b5b949f1-e72c-41e4-9889-43975fd13928)


## Visual -6
Event Bar:
![image](https://github.com/user-attachments/assets/98bfd703-d415-4061-ad2e-c9e782ea0e47)
