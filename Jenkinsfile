pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', 
                url: 'https://github.com/Pradeepa-1602/push-pull-using-ssh'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Build Started"'
                sh 'pwd'
                sh 'ls'
            }
        }
    }
}
