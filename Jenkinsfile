pipeline {
    agent any

    environment {
        DEBUG = 'true'
    }

    options {
        disableConcurrentBuilds()
        retry(2)
        timeout(time: 10, unit: 'MINUTES')
        timestamps()
    }
    
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
            }
        }
    }

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
                // error "manual failed"
            }
        }
    }

    post {
        always {
            sh 'echo this runs always'
        }
        failure {
            sh 'echo this runs during build failue'
        }
        success {
            sh 'echo this runs during duild success'
        }
    }
}