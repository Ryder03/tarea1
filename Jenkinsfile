pipeline {
    agent any

    stages {

    	stage('Clone sources') {
        	git clone https://github.com/gnarula/django-ribbit.git
    	}

        stage('Make a virtual environment') {
            steps {
                sh 'virtualenv --no-site-packages ribbit_env'
            }
            steps {
                sh 'source ribbit_env/bin/activate'
            }
            steps {
                sh 'pip install Django==1.6 South'
            }
            steps {
                sh 'cd django-ribbit/'
            }
            steps {
                sh 'python manage.py syncdb'
            }
            steps {
                sh 'python manage.py migrate ribbit_app'
            }
            steps {
                sh 'python manage.py runserver'
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
