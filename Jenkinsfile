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
                sh 'go build main.go'
            }
        }
        
        stage('SUCCESS') {
            steps {
                sh 'echo success'
            }
        }        
    }
}
