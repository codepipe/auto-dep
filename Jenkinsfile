pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage ("pull code") {
            steps {
                git branch: 'main', credentialsId: 'eec330e2-1e4c-4a64-bfbe-3f5d96c0c768', url: 'https://github.com/codepipe/auto-dep.git'  
            }
        }
        stage ("build") {
            steps {
                sh "mvn install"
            }
        }
        stage ("deploy to artifactory") {
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'google', classifier: '', file: 'google.war', type: 'war']], credentialsId: 'super', groupId: 'aws', nexusUrl: '3.89.20.99:8081/repository/apponix-nexus/', nexusVersion: 'nexus3', protocol: 'http', repository: 'http://3.89.20.99:8081/repository/apponix-nexus/', version: '1.0-SNAPSHOT
            }
        }
    }
}
