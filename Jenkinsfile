pipeline {
    agent any // Specifies where the entire pipeline will execute
    
    environment {
        SAMPLE_ENV = "SAMPLE"
    }

    options {
        timeout(time: 10, unit: 'MINUTES') // Sets a timeout for the pipeline
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps {              
                script{
                    sh """ 
                    echo "This is a multi-line script block"
                    echo $SAMPLE_ENV
                    #sleep 10
                    env
                    
                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.DEPLOY}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}"
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script{
                    sh """
                        echo "testing"
                    """
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post { // Actions to run after the pipeline finishes
        always {
            echo 'I will always say Hello again!'
            cleanWs() // Cleans up the workspace
        }
        success {
            echo 'I succeeded!'
        }
        failure {
            echo 'I failed!'
        }
        aborted {
            echo 'pipeline is aborted'
        }
    }
}
