pipeline {
    agent any
     environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }

    stages {
        stage('Checkout') {
            steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/orel199973/TF_Lambda_API_Gateway.git']]])            

          }
        }

        stage('Init') {       
            steps {
                sh 'terraform init --auto-approve'
            }
        }

        stage('Apply') {         
            steps {
                sh "terraform apply --auto-approve"
            }
        }
        
    }
}