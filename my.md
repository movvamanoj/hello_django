name: Deploy to Amazon Linux EC2

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: amazon-linux-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Setup SSH
      uses: webfactory/ssh-agent@v0.5.3
      with:
        ssh-private-key: ${{ secrets.SSH_PRIVATE_KEY }}

    - name: Clone repository
      run: git clone https://github.com/movvamanoj/hello_django.git ./django_project

    - name: Install dependencies
      run: |
        sudo yum install python3-pip
        pip install django

    - name: Install project dependencies
      run: |
        cd ./django_project
        pip install -r requirements.txt

    - name: Run migrations 
      run: |
        cd ./django_project
        python3 manage.py migrate

    - name: Start Django
      run: |
        cd ./django_project
        python3 manage.py runserver 0.0.0.0:8000