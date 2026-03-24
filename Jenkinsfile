pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'python3 --version'
                sh 'ls -l'
            }
        }

        stage('Test') {
            steps {
                sh 'python3 test_calculator.py'
            }
        }

        stage('Deploy') {
    steps {
        sh '''
        scp -o StrictHostKeyChecking=no calculator.py ec2-user@13.63.239.173:/home/ec2-user/
        '''
    }
}

    }
}
