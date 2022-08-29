pipeline {
    agent any
    
    stages {
        stage ('Build') {
            agent {
                docker {
                    image 'ubuntu'
                    args '--user root'
                }
            }
                steps{
                    sh 'apt-get update'
                    sh 'apt install build-essential'
                }
                }
            }
        }
    
