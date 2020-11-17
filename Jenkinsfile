pipeline {
    agent any
    stages {
        stage('Pull latest image') {
            steps {
                bat "docker pull nitinmanojkumar/selenium-docker"
            }
        }
        stage('Start Grid') {
            steps {
                bat "cd C://JenkinsSlave//workspace//SELENIUM_DOCKER_RUNNER && docker-compose up -d hub chrome ff"
            }
        }      
        stage('Run Test') {
            steps {
                bat "cd C://JenkinsSlave//workspace//SELENIUM_DOCKER_RUNNER && docker-compose up search-module-ff search-module-chrome"
            }
            
        }
   }
    post{
        always{
            archiveArtifacts artifacts: 'output/**'
            bat "cd C://selenium-docker-runner && docker-compose down"
        }
    }
}