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
            
            
        AWS_ACCESS_KEY_ID     = credentials('oming')
        AWS_SECRET_ACCESS_KEY = 'oming'
    }
    stages {
        stage('Example') {
            environment {
                DEBUG_FLAGS = '-g'
            }
            steps {
                sh 'printenv'
                echo ${AWS_ACCESS_KEY_ID}
                echo ${AWS_SECRET_ACCESS_KEY}
            }
        }
    }
}

