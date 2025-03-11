pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ hello.cpp -o hello_exec'
                }
            }
        }

        stage('Test') {
    steps {
        script {
            sh './hello_exec'
            sh 'exit 1'  // This line forces an error, causing the pipeline to fail
        }
    }
}


        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}
