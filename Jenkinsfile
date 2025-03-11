pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '/main']],
                    userRemoteConfigs: [[url: 'https://github.com/BasavarajSAtnoor/PES1UG22CS133_jenkins']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS133-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
