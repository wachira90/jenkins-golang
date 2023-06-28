pipeline {
    agent { 
        docker { 
            image 'golang:1.19.1-alpine' 
            args '-v ${WORKSPACE}/:/.cache --network=host'
        } 
        
    }
    stages {
        
        stage('CHECK VERSION') {
            steps {
                sh 'go version'
                sh 'pwd'
                sh 'which go'
                sh 'rm -f go.*'
//                sh 'mkdir -p .cache'
//                sh 'printenv'
            }
        }
        
        stage('BUILD GOLANG') {
            steps {
//                 golang-version THIS UP PARENT FOLDER
                sh 'go mod init jenkins-golang'
                sh 'go mod tidy'
                sh 'go build'
            }
        }
        
        stage('SUCCESS') {
            steps {
//                sh 'echo success'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                sh 'chmod 0775 jenkins-golang'
                sh 'exit'
            }
        }        
    }
}
