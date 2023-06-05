# Assignment 1 CLO 835

# 1. Login in to the ec2 instance
```ssh -i <ssh-key> <eip>```

# 2. Install docker and update the images
```sudo yum update -y``` 

```sudo yum install docker -y```

```sudo systemctl start docker``` 

```sudo systemctl status docker```

#3. Update the aws credentials 

```vi ~/.aws/credentials```

#4. Export the ECR and login

```export ECR = <ecr uri>```
```aws ecr get-login-password --region us-east-1 | docker login -u AWS ${ECR} --password-stdin```

#5. 

# Running application locally
pip3 install -r requirements.txt
sudo python3 app.py
# Building and running 2 tier web application locally
### Building mysql docker image 
```docker build -t my_db -f Dockerfile_mysql . ```

### Building application docker image 
```docker build -t my_app -f Dockerfile . ```

### Running mysql
