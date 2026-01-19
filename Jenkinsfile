pipeline {
    agent any // Specifies where the entire pipeline will execute
    
    envoironment {
        SAMPLE_ENV = "SAMPLE"
    }
    stages {
        stage('Build') {
            steps {              
                script{
                    sh """ 
                    echo "This is a multi-line script block"
                    echo $SAMPLE_ENV
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
    }
}
