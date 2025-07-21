pipeline {
    agent any
    stages {
        stage ('Code') {
            steps {
                git 'https://github.com/nagavenis2025/web-app.git'
            }
        }
        
    stage ('Build') {
        steps {
            sh 'mvn clean package'
        }
    }
    stage ('Artifact') {
        steps {
            nexusArtifactUploader artifacts: [[artifactId: 'myweb', classifier: '', file: 'target/myweb-8.6.6.war', type: 'war']], credentialsId: 'nexus', groupId: 'in.javahome', nexusUrl: '13.48.68.134:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'new-repo', version: '8.6.6'
        }
    }
    }
}
