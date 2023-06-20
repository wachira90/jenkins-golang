pipeline {
    agent { 
        docker { 
            image 'golang:1.19.1-alpine' 
            args '--network=host'
        } 
        
    }
    stages {
        
        stage('test environment') {
            steps {
                sh 'go version'
                sh 'pwd'
            }
        }
        
        stage('build golang') {
            steps {
                sh 'go build main.go'
            }
        }
        
        stage('success') {
            steps {
                sh 'echo success'
            }
        }        
    }
}
