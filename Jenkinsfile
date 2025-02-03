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

        stage('SonarQube Analysis') {
            steps {
                sh ''' 
                    $SCANNER_HOME/bin/sonar-scanner \
                    -Dsonar.host.url=http://13.235.42.79:9000/ \
                    -Dsonar.login=sqa_8910619eb7e977b6f93187ab5b2acb00313bfbdb \
                    -Dsonar.projectKey=Ekart \
                    -Dsonar.projectName=Ekart \
                    -Dsonar.java.binaries=.
                '''
            }
        }
    }
}
