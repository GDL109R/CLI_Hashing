pipeline {
    agent any

    environment {
            // Define the name of the jar file that your Maven build produces
            JAR_NAME = "java-project-1.0-SNAPSHOT.jar"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/GDL109R/CLI_Hashing.git'
            }
        }

        stage('Build with Maven') {
            steps {
                script {
                    // Execute Maven build
                    sh 'mvn clean package'
                }
            }
        }

        stage('Show JAR Directory') {
            steps {
                script {
                    // Find and echo the directory of the built JAR file
                    def jarPath = sh(script: "find ${WORKSPACE} -name ${JAR_NAME}", returnStdout: true).trim()
                    if (jarPath) {
                        echo "JAR file created at: ${jarPath}"
                    } else {
                        echo "JAR file not found"
                    }
                }
            }
        }
    }


}