FROM python:3.10-slim-buster

# Inside the Container
# make a new folder insde container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# this  contains the libraries want to install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Ouside Container -> Inside Container
# . means everything in the current difrectory
# first period . /backend-flask (outside container)
# second period . /backend-flask (inside container)
COPY . .

# Set Environment Variables (Env Vars)
# Inside Conntainer and will remain set when the containr is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
