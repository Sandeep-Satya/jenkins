pipeline {
    agent any // Specifies where the entire pipeline will execute

    stages {
        stage('Build') {
            steps {
                echo 'Building..' // A basic Pipeline step to print a message
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
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
        }
    }
}
