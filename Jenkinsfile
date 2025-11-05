pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/<your-username>/git-cache-maintenance.git'
            }
        }
        stage('Git Cache Maintenance') {
            steps {
                echo 'Running Git Cache Cleanup...'
                sh 'git gc --prune=now --aggressive'
                echo 'Cleanup completed successfully.'
            }
        }
    }
    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
