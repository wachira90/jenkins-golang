pipeline {
    agent { 
        docker { 
            image 'golang:1.19.1-alpine' 
            args '--network=host'
        } 
        
    }
    stages {
        
        stage('CHECK VERSION') {
            steps {
                sh 'go version'
                sh 'pwd'
//                sh 'printenv'
            }
        }
        
        stage('BUILD GOLANG') {
            steps {
//                 golang-version THIS UP PARENT FOLDER
                sh 'go mod init golang-version'
                sh 'go mod tidy'
                sh 'go build'
            }
        }
        
        stage('SUCCESS') {
            steps {
                sh 'echo success'
                sh 'exit'
            }
        }        
    }
}
