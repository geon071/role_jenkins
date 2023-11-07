pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Checkout') {
            steps{
                git branch: 'main', credentialsId: 'ccff9132-4ad2-4920-b403-a6ce059803fb', url: 'git@github.com:geon071/role_jenkins.git'
            }
        }
        stage('Start Molecule'){
            steps{
                dir('extensions'){
                    sh 'molecule test'
                }
                // Clean workspace after testing
                cleanWs()
            }
        }
    }
}