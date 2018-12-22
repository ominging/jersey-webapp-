pipeline {
    agent any 
    environment {
        // Using returnStdout
        CC = """${sh(
                returnStdout: true,
                script: 'echo "clang"'
            )}""" 
        // Using returnStatus
        EXIT_STATUS = """${sh(
                returnStatus: true,
                script: 'exit 1'
            )}"""
            
            
        //AAWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
        AWS_SECRET_ACCESS_KEY = 'jenkins-aws-secret-access-key'
    }
    stages {
        stage('Example') {
            environment {
                DEBUG_FLAGS = '-g'
                 AWS_SECRET = 'jenkins-aws-secret'
            }
            steps {
                sh 'printenv'
                echo "${AWS_SECRET}"
                echo "${AWS_SECRET_ACCESS_KEY}"
            }
        }
    }
}

