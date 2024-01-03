This is an experiment meant to explore the usage of MLFlow with DagsHub


# MLflow-Basic-Operations





## for DagsHub

MLFLOW_TRACKING_URI=https://dagshub.com/timothyafolami/mlflow-tutorial.mlflow \
MLFLOW_TRACKING_USERNAME=timothyafolami \
MLFLOW_TRACKING_PASSWORD=0e4ec151277a77e5cfb21df9b181c26925a39a7c \
python script.py

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/timothyafolami/mlflow-tutorial.mlflow 
export MLFLOW_TRACKING_USERNAME=timothyafolami 
export MLFLOW_TRACKING_PASSWORD=0e4ec151277a77e5cfb21df9b181c26925a39a7c 
```

## MLflow on AWS Setup:

1. Login to AWS console
2. Create IAM user with AdministratorAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on EC2 machine

```bash
sudo apt update

sudo apt install python3-pip

sudo pip3 install pipenv

sudo pip3 install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell

## Then set aws credentials
aws configure

#Finally 
mlflow server -h 0.0.0.0 --default-artifact-root s3://timmy-bucket-1

#open public IPV4 DNS to the port 5000


#set uri in your local terminal and in your code
export MLFLOW_TRACKING_URI=http://ec2-16-171-197-80.eu-north-1.compute.amazonaws.com:5000/
```