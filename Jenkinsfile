

pipeline {
    agent any
    
    stages {
        stage('Build app') {
            steps {
                 scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/manthanindane/Assignment-8.git']])
                
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    bat 'docker build -t jenkinsdocker .'
                }
            }
        }
        
        stage('Rename Image Tag') {
            steps {
                script {
                    bat 'docker tag jenkinsdocker manthanindane/jenkinsdockerapp:image1'
                }
            }
        }
        
        stage('Push Image to docker Hub') {
            steps {
                script {
                    bat 'docker login -u manthanindane -p manthan1422'
                    bat 'docker push manthanindane/jenkinsdockerapp:image1'
                }
            }
        }
    }
}
