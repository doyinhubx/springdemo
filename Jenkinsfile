pipeline {
    agent any

    environment {
        JAVA_HOME = '/usr/lib/jvm/java-21'
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh 'chmod +x ./mvnw'  // Add execute permission
                sh './mvnw clean package -DskipTests'
            }
        }
    }

    post {
        success { echo 'Build succeeded!' }
        failure { echo 'Build failed.' }
    }
}