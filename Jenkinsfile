pipeline {
    agent any 
    stages {
        stage ("PULL code from GIT") {
            steps {
                git branch: 'main', credentialsId: '90ce3b4e-c3da-4cf0-b728-e1a300da9085', url: 'https://github.com/codepipe/auto-dep.git'
            }
        }
        stage ("compile the code") {
            steps {
                sh "mvn install"
            }
        }

    }
}
