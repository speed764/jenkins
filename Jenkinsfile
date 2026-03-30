pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo "Cloning repository..."
                checkout scm
            }
        }

        stage('Verify Files') {
            steps {
                echo "Listing project files..."
                bat 'dir'
            }
        }

    }

    post {
        success {
            echo "✅ Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed."
        }
        always {
            echo "🔄 Pipeline finished."
        }
    }
}
