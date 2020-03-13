# superset-tink

run docker-compose up -d --build

Once everything is up, run docker exec -itu root {contaienr id} /bin/bash

RUN THE FOLLOWING COMMANDS
# Install superset
pip install apache-superset

# Initialize the database
superset db upgrade

# Create an admin user (you will be prompted to set a username, first and last name before setting a password)
export FLASK_APP=superset

flask fab create-admin

# Load some data to play with
superset load_examples

# Create default roles and permissions
superset init
chmod 777 -R /usr/local/lib/python3.6/site-packages/superset/
