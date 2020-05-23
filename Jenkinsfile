pipeline {
    agent {
        docker {
            image 'ruby'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building or resolve Dependencies'
                sh 'bundle install'
            }
        }
        stage('Test') {
            steps {
                echo 'Running regression tests'
            }
        }
        stage('UAT') {
            steps {
                echo 'Wait for User Acceptence'
                input(message: 'Go to production?', ok: 'Yes')
            }
        }
        stage('Prod') {
            steps{
                echo "WebApp is Ready :)"
            }
        }
    }
}