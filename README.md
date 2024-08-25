# Streamlit App Deployment on EC2

**This repository** contains a Streamlit application and instructions for deploying it on an AWS EC2 instance.

## Prerequisites

- **An AWS account**
- **An EC2 instance with Ubuntu**
- **Basic knowledge of using SSH to connect to your EC2 instance**

## Setup Instructions
### 1. Launch an EC2 Instance

1. Log in to the [AWS Management Console](https://aws.amazon.com/console/).
2. Launch a new EC2 instance with Ubuntu.

### 2. Connect to Your EC2 Instance
Use SSH to connect to your EC2 instance:

ssh -i "your-key.pem" ubuntu@your-ec2-public-ip

### 3. Prepare the Environment
Run the following commands to set up your EC2 instance:

sudo apt update

sudo apt-get update

sudo apt upgrade -y

sudo apt install git curl unzip tar make sudo vim wget -y

### 4. Clone the Repository
Clone this repository to your EC2 instance:

git clone "https://github.com/your-username/your-repository.git"

cd your-repository

### 5. Install Python and Pip
Install Python and pip:

sudo apt install python3-pip

### 6. Install Dependencies
Install the required Python packages:

pip3 install -r requirements.txt

or

pip3 install --break-system-packages -r requirements.txt


### 7. Run the Streamlit App
Temporary Running:

python3 -m streamlit run app.py

Permanent Running (using nohup to keep it running in the background):

nohup python3 -m streamlit run app.py &

### 8. Configure Security Group
Ensure that port 8501 is open in the EC2 instance’s security group settings:

Go to the EC2 Dashboard.

Select your instance.

In the "Description" tab, click on the security group.

Edit the inbound rules to allow traffic on port 8501.

### 9. Access the Streamlit App
Open a web browser and navigate to:
http://<your-ec2-public-ip>:8501
You should now see your Streamlit app running.
