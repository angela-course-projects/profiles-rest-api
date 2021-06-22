# Profiles REST API

Source code for profiles REST API project built following Udemy's [Build a Backend REST API with Python & Django - Beginner](https://www.udemy.com/course/django-python/) course.

Instructor's cheat sheet can be found [here](https://github.com/LondonAppDev/build-a-backend-api-python-drf-beginner-cheat-sheet/blob/master/README.md).

## Set Up Development Server Using Vagrant

We use [Vagrant](https://www.vagrantup.com/) to build a local development server.

### Initialize Vagrant
We used the `ubuntu/bionic64` box. More available boxes can be found [here](https://app.vagrantup.com/boxes/search).
```bash
vagrant init ubuntu/bionic64
```
This step creates `Vagrantfile` in the root directory. We customized the Vagrantfile based on our needs.

### Create server
```bash
vagrant up
```
### Connect to server
```bash
vagrant ssh
```
### Access synced folder
Vagrant syncs your project files to the `/vagrant` directory on your guest machine.
```bash
cd /vagrant
```
### Exit server
```
exit
```

## Create a Django Application
### Create Python Virtual Environment 
First, create a Python virtual environment in the Vagrant server. Create the venv in the home directory so it doesn't sync with our local machine.
```bash
cd /vagrant
python -m venv ~/env
```
Activate the virtual environment.
```bash
source ~/env/bin/activate
```
To deactivate the virtual environment.
```bash
deactivate
```
### Create Django project
Create a new Django project called `profiles_project` in the current directory.
```bash
django-admin.py startproject profiles_project .
```
### Create a new app within the project
```bash
python manage.py startapp profiles_api
```
### Start Django development server
```bash
python manage.py runserver 0.0.0.0:8000
```