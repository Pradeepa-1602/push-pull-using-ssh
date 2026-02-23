pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git url: 'https://github.com/Pradeepa-1602/push-pull-using-ssh/new/main',
                    branch: 'main',
                    credentialsId: 'git-credentials-id'
            }
        }

        stage('Commit & Push') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'git-credentials-id',
                    usernameVariable: 'USERNAME',
                    passwordVariable: 'PASSWORD'
                )]) {

                    sh '''
                        git config user.name "jenkins"
                        git config user.email "jenkins@gmail.com"

                        echo "Updated by Jenkins" >> test.txt

                        git add .
                        git commit -m "Auto commit"
                        git push https://${USERNAME}:${PASSWORD}@github.com/your-username/your-repo.git main
                    '''
                }
            }
        }
    }
}
