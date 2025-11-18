pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Dynamicpoders/git-cache-maintenance-in-jenkins.git'
            }
        }

       stage('Disk Space Before Cleanup') {
    steps {
        echo '📊 Disk space BEFORE cleanup'
        sh 'dir C:\\'
    }
}

stage('Disk Space After Cleanup') {
    steps {
        echo '📊 Disk space AFTER cleanup'
        sh 'dir C:\\'
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
