pipeline {
    agent any

    stages {
        stage ('build') {
            steps {
                sh 'echo this is build'
            }
        }

        stage ('scan the code') {
            steps {
                sh 'echo scan the code'
            }
        }

        stage ('push the build to ECR') {
            steps {
                sh 'echo code push to ECR'
            }
        }

        stage ('create docker image') {
            steps {
                sh 'echo create docker image'
            }
        }

        stage ('deploy in k8') {
            steps {
                sh 'echo deploy in k8'
            }
        }
    }
}