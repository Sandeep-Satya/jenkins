pipeline {
    agent any // Specifies where the entire pipeline will execute

    stages {
        stage('Build') {
            steps {
                
                script{
                    sh """ 
                    echo "This is a multi-line script block"

                    """
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                script{
                    sh """
                        echo "Building"
                    """
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
