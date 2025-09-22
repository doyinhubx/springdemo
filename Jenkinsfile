pipeline {
    agent any

    environment {
        JAVA_HOME = '/opt/java/jdk-21'  // Correct path from your Dockerfile
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Build') {
            steps {
                sh 'echo "JAVA_HOME is set to: $JAVA_HOME"'
                sh 'java -version'
                sh 'chmod +x ./mvnw'
                sh './mvnw clean package -DskipTests'
            }
        }
    }

    post {
        success { echo 'Build succeeded!' }
        failure { echo 'Build failed.' }
    }
}