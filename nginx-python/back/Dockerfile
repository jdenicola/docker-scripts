# Using Python 3.8.7
From python:3.8.7

# Container Working Directory
WORKDIR /backend

# Adding every file to /backend on container
ADD . /backend

# Installing Python dependencies (Stored in requirements.txt in this folder)
RUN pip install -r requirements.txt

# Optional, if using Flask, run it as uwsgi. Otherwise, set your own script here.
# i.e. CMD ["python3", "yourfile.py"]
CMD ["uwsgi", "app.ini"]
