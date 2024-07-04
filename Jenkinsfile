pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // Clean workspace before cloning
                    deleteDir()
                    // Clone the repository
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                              userRemoteConfigs: [[url: 'https://github.com/GDL109R/CLI_Hashing', credentialsId: 'Github-Token']]])

                    sh "ls"
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                sh
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}