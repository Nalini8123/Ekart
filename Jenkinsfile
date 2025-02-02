pipeline {
    agent any  // Runs on any available Jenkins agent

    environment {
        GITHUB_REPO = 'https://github.com/Nalini8123/Ekart.git'
       
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning repository...'
                git branch: 'main', url: "${GITHUB_REPO}"
            }
        }
    }
}
