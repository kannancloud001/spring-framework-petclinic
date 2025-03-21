pipeline {
    agent any
    
    
    stages{
        stage('Build Maven'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kannancloud001/spring-framework-petclinic.git']])
                
            }
        }
        stage('Build and Test') {
            steps {
                script {
                    sh 'mvn clean package'
                }
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t kannandolmites/java-maven .'
                }
            }
        }
    }
    
}    
