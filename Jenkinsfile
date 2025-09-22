pipeline {
    agent any

    environment {
        JAVA_HOME = '/opt/java/openjdk'  // This is the correct path
        PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    }

    stage('Build') {
        steps {
            sh 'java -version'
            sh 'ls -la ~/.m2/repository/ || echo "No Maven cache yet"'
            sh 'chmod +x ./mvnw'
            sh './mvnw clean package -DskipTests'
        }
    }

    post {
        success { echo 'Build succeeded!' }
        failure { echo 'Build failed.' }
    }
}

