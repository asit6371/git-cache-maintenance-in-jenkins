pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/shreepalilenka/git-cache-maintenance-in-jenkins'
            }
        }

       stage('Disk Space Before Cleanup') {
    steps {
        echo '📊 Disk space BEFORE cleanup'
        bat 'dir C:\\'
    }
}

stage('Disk Space After Cleanup') {
    steps {
        echo '📊 Disk space AFTER cleanup'
        bat 'dir C:\\'
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
