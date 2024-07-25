pipeline {
    agent {
        label 'maven'
    }

    stages {
        stage('Clone-code') {
            steps {
                git branch: 'main', url: 'https://github.com/OPerezSandoval/tweet-trend.git'
            }
        }
    }
}
