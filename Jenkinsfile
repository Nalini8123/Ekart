pipeline {
    agent any

    tools {
        jdk 'jdk'
        maven 'maven'
    }

    environment {
        SCANNER_HOME = tool 'sonar-scanner'  // Ensure this matches Jenkins Global Tool Name
    }

    stages {
        stage('Git checkout') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/jaiswaladi246/Ekart.git'
            }
        }

        stage('Git compile') {
            steps {
                sh "mvn clean compile"
            }
        }
    }
}

