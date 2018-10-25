pipeline {
    agent any

    stages {

        stage ('cosas') {
            steps {
                sh 'virtualenv --no-site-packages ribbit_env'
            }
        stage ('cosas1') { 
            steps {
                sh 'source ribbit_env/bin/activate'
            }
        }
        stage ('cosas2') {
            steps {
                sh 'pip install Django==1.6 South'
            }
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

        stage ('Build') {
            steps {
                echo 'Building..'
            }
        }

        stage ('Deploy') {
            steps {
                echo 'Code deployed'
            }
        }

    }
}
