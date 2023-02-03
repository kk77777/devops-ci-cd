pipeline{
    agent any
    tools{
        maven 'Maven-3.5.0'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kk77777/devops-ci-cd']]])
                sh 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                sh 'docker build -t kumark77777/devops-integration .'
                }
            }
        }
        stage('Push image to hub'){
            steps:{
                
            }
        }
    }
        
}
