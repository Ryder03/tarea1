pipeline {
    agent any

    stages {

    	stage('Clone sources') {
        	git clone https://github.com/gnarula/django-ribbit.git
    	}

        stage('Make a virtual environment') {
            steps {
                bash 'virtualenv --no-site-packages ribbit_env'
            }
            steps {
                bash 'source ribbit_env/bin/activate'
            }
            steps {
                bash 'pip install Django==1.6 South'
            }
            steps {
                bash 'cd django-ribbit/'
            }
            steps {
                bash 'python manage.py syncdb'
            }
            steps {
                bash 'python manage.py migrate ribbit_app'
            }
            steps {
                bash 'python manage.py runserver'
            }
        }

        stage('Build') {
            steps {
                echo 'Building..'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Code deployed'
            }
        }

    }
}