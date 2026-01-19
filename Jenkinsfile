pipeline {
    agent any // Specifies where the entire pipeline will execute
    
    environment {
        SAMPLE_ENV = "SAMPLE"
    }

    options {
        timeout(time: 10, unit: 'SECONDS') // Sets a timeout for the pipeline
        disableConcurrentBuilds()
    }
    stages {
        stage('Build') {
            steps {              
                script{
                    sh """ 
                    echo "This is a multi-line script block"
                    echo $SAMPLE_ENV
                    sleep 10
                    env
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
