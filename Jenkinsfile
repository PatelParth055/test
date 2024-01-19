pipeline {
    agent any
    parameters {
        string (name: 'parth', defaultValue: 'harsh', description: 'who are you')
        booleanParam (name: 'ismale', defaultValue: 'yes', description: '')
        choice (name: 'city', choices: ['yeshwantpur','mumbai','bangalore'], description: '')
        
    }

    stages {
        stage('test run a command') {
            steps {
                sh '''
                pwd
                date
                '''
            }
        }    
        stage('Environment variables') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${parth}"'
                sh 'echo "${ismale}"'
                sh 'echo "${city}"'
                
            }    
        }
        stage('continue') {
            input{
                message "Do u want to continue"
                ok"conti..."
            }
            
            steps {
                echo 'deploy on test server'
            }
        }
        stage('production') {
            steps {
                echo123 'deploy on production'
            }
        } 
        
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { echo 'failed'}
        success { echo 'sucess'}
    }
}
