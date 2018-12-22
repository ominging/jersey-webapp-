/**
pipeline {
    agent any
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')

        file(name: "FILE", description: "Choose a file to upload")
    }
    stages {
        stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
    }
}
**/
pipeline {
    agent any
    options { 
        timestamps() 
            }
    triggers{ 
        //pollSCM('*/2 * * * *')
        cron('*/2 * * * *')
            }
    
    stages {
        stage('Example') {
            environment {
                AN_ACCESS_KEY = 'my-prefined-secret-text'
            }
            steps {
                echo 'Hello World'
                echo "Hello World ${AN_ACCESS_KEY}"
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}
