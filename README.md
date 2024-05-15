# MLflow-Basic-Operation




## For Dagshub:

MLFLOW_TRACKING_URI=https://dagshub.com/uchihamadara91/MLflow-Basic-Operation.mlflow \
MLFLOW_TRACKING_USERNAME=uchihamadara91 \
MLFLOW_TRACKING_PASSWORD=41fb6c30248d1714dbe5ee06e83c290d022fbdf2 \
python script.py



```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/uchihamadara91/MLflow-Basic-Operation.mlflow

export MLFLOW_TRACKING_USERNAME=uchihamadara91

export MLFLOW_TRACKING_PASSWORD=41fb6c30248d1714dbe5ee06e83c290d022fbdf2


``` 


# Mlflow on AWS

## MLflow on AWS Setup:

1. Login to AWS Console
2. Create IAM user with AdministratorAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a S3 bucket
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

# Finally
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-buc18

#open Public IPv4 DNS to the port 5000

#set uri in your local terminal and in your code

export MLFLOW_TRACKING_URI=http://ec2-13-50-239-22.eu-north-1.compute.amazonaws.com:5000/

```