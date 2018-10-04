pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "mvn package -DskipTests"
            }
        }
        steps('UploadArtifact') {
            nexusArtifactUploader(
                artifactId: 'com.liatrio.sprint-petclinic',
                file: 'target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar',
                groupId: 'spring',
                type:'jar',
                nexusPassword: 'admin123',
                nexusUrl: 'localhost:8081/nexus',
                nexusUser: 'admin',
                nexusVersion: 'nexus3',
                protocol: 'http',
                repository: 'maven-snapshots',
                version: '2.0.0-SNAPSHOT'
            )
        }
    }
}