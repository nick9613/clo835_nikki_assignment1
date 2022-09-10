# Install the required MySQL package

sudo apt-get update -y
sudo apt-get install mysql-client -y

# Running application locally
pip3 install -r requirements.txt
sudo python3 app.py

# Building mysql docker image 
docker build -t my_db -f Dockerfile_mysql .

# Building application docker image 
docker build -t my_app -f Dockerfile . 

# Running mysql
docker run -e MYSQL_ROOT_PASSWORD=pw -p 3307:3306 my_db


# Get the IP of the database and export it as DBHOST variable
docker inspect <container_id>


# Example when running DB runs as a docker container and app is running locally
export DBHOST=127.0.0.1
export DBPORT=3307

# Example when running DB runs as a docker container and app is running locally
export DBHOST=172.17.0.2
export DBPORT=3306

export DBUSER=root
export DATABASE=employees
export DBPWD=pw
export APP_COLOR=pink

# Run the application, make sure it is visible in the browser
docker run -p 8080:8080  -e DBHOST=$DBHOST -e DBPORT=$DBPORT -e  DBUSER=$DBUSER -e DBPWD=$DBPWD  my_app# clo835_fall2022_assignment1
