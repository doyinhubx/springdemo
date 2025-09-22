pipeline {
    agent any

    stages {
        stage('Debug') {
            steps {
                sh 'pwd'
                sh 'ls -la'
                sh 'which java'
                sh 'java -version'
                sh 'echo "JAVA_HOME: $JAVA_HOME"'
                sh 'echo "PATH: $PATH"'
                script {
                    // Try different Java paths
                    def possiblePaths = [
                        '/opt/java/jdk-21',
                        '/usr/lib/jvm/java-21', 
                        '/usr/lib/jvm/default-java'
                    ]
                    possiblePaths.each { path ->
                        sh "if [ -d '$path' ]; then echo 'Found Java at: $path'; fi"
                    }
                }
            }
        }
    }
}