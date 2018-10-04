pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "mvn package -DskipTests"
            }
        }
        stage('UploadArtifact') {
            steps {
                sh "mvn deploy:deploy-file -DgroupId=com.liatrio -DartifactId=project -Dversion=1.0.0-SNAPSHOT -DgeneratePom=true -Dpackaging=jar -DrepositoryId=nexus -Durl=http://localhost:8081/repository/maven-snapshots -Dfile=target/spring-petclinic-2.0.0.BUILD-SNAPSHOT.jar"
            }
        }
    }
}