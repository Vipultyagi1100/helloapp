pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'mvn test'
            }
        }
         }
        stage('package') {
            steps {
                echo 'packaging...'
                sh 'mvn package'
            }
        
        }
         }
        stage('containerize') {
            steps {
                echo 'conatinerize...'
                sh 'docker build -t hello-image'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'kubectl apply -f hello-pod.yaml'
            }
        }
    }
}


