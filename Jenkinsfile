pipeline {
    agent any

    stages {
        stage('build') {
            steps {
             
	       sh 'docker build -t python2/app .'
            }
    
        }
        stage('push') {
            steps {
        sh 'aws ecr get-login-password --region eu-central-1 | docker login --username AWS --password-stdin 815197024081.dkr.ecr.eu-central-1.amazonaws.com '
        sh 'docker tag  python2/app 815197024081.dkr.ecr.eu-central-1.amazonaws.com/python.app:2'
        sh 'docker push 815197024081.dkr.ecr.eu-central-1.amazonaws.com/python.app:2'
            }

        }

    }
}
