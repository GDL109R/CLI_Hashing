pipeline {
    agent any

    environment {
            // Define the name of the jar file that your Maven build produces
            JAR_NAME = "target/java-project-1.0-SNAPSHOT.jar"
            JAR_ARGUMENT = "\"words\""
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
                    powershell 'mvn clean package'
                }
            }
        }

        stage('Show JAR Directory') {
            steps {
                script {
                    powershell "java -jar ${jarPath} ${JAR_ARGUMENT}"
                }
            }
        }
    }


}