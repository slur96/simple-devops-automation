pipeline {
    agent any
    tools{
        maven 'maven'
    }
    
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/slur96/simple-devops-automation.git']]])
                sh 'mvn clean install'
            }
        }
    stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t samuel78996/kubernetes .'
                }
            }
        }
    }    
}
