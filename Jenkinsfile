pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your repository
                git 'https://github.com/abhishek-046-tech/CI-CD.git'
            }
        }
        
        stage('Set Up Python Environment') {
            steps {
                // Set up Python and install dependencies
                sh '''
                python -m pip install --upgrade pip
                pip install pytest
                '''
            }
        }
        
        stage('Run Tests') {
            steps {
                // Run the tests
                sh 'pytest'
            }
        }
    }
    
    post {
        always {
            // Clean up or perform other actions after the pipeline runs
            echo 'Cleaning up...'
        }
        
        success {
            echo 'Tests passed!'
        }
        
        failure {
            echo 'Tests failed!'
        }
    }
}
