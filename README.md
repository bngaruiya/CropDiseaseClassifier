# CropDiseaseClassifier
This classifier utilizes leafs of plants derived from 15 crop disease classes to identify and classify the disease a particular image of a plant leaf may be suffering from.
The dataset used is from the [plant village kaggle api](https://www.kaggle.com/emmarex/plantdisease).

## Configuration
You will want to put all the code in its own specific folder. This is quite helpful when using GDrive to build different projects.
- Clone this repo and put the crop_diseases.ipynb file in the root folder of your project.
- On your Google Colaboratory `crop_diseases.ipynb` file, click on **Runtime => Change Runtime Type**. Under Hardware Accelerator, ensure **GPU** is selected. Restart the runtime environment by going to **Runtime => Factory Reset Runtime** and click **Yes**.
- To run a code cell press `shift + enter`.
- Run the first cell. It gives you an auth link to connect to your Gdrive. Click `Allow` which redirects you to an auth success link with an auth code. Copy and paste the auth code into the prompt window on the cell. That will link the .pynb file to your project folder on GDrive.
- Navigate to [Kaggle](https://www.kaggle.com/). Navigate to your profile and select **My Account**. Scroll down to the **API** section and click on **Create New API Token**. An api is automatically generated and you will be prompted to download the file. Download it and place it in your project root directory on Gdrive.
- NOTE: if this is your first time working with deep learning models on Gdrive, I would highly suggest you stick to the defaults, as setup on the .pynb file. However, you could change them to your liking. The defaults include the naming convention used.
- Navigate to this [plant village kaggle dataset link](https://www.kaggle.com/emmarex/plantdisease). On your right, next to the **New Notebook** button are three vertical dots. click on them and select **Copy API Command**. Paste that into cell three. Alternatively you could uncomment the command as is in the cell. That too will work perfectly. This will allow us to download the zipped dataset from kaggle
- Uncomment the unzip command on cell four and run it too. This will unzip the downloaded file above to provide us our images dataset.
- **Important** Cell three and four should be run only once. Once you are done, comment the cells. Thisway, they will not have any effect on subsequent runs.
- I manually split the dataset into training, validation and testing datasets. I did this by creating three new folders in the plantvillage main folder, train, val and test. I then manually split the dataset as below:
    1. train 0.7
    2. val 0.2
    3. test 0.1
    You could also try a 0.8, 0.1, 0.1 split. However you prefer is fine.
   Ensure that the train, val and test folders are within the plantVillage folder.
   You could also use dataset subsampler though I thought to use this manual method to keep things simple.

- Run through the rest of the code.
- Once you are finished, you should have a model_transfer.pt and a classes.json file in your project directory on Gdrive.
- Download these two files and follow the instructions on [Crop Disease Django API](https://github.com/bngaruiya/Build4SDG-Team252) repo to set up a django REST api which serves the classifier to a frontend for consumption.
