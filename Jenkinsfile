pipeline {
    agent any

    tools {
        jdk 'jdk'
        maven 'maven'
    }

    environment {
        SCANNER_HOME = tool 'sonar-scanner'  // Ensure this matches Jenkins Global Tool Name
        JAVA_HOME = '/usr/lib/jvm/java-11-openjdk-amd64'  // Set JAVA_HOME
        MAVEN_HOME = '/opt/maven'  // Set MAVEN_HOME
        PATH = "$MAVEN_HOME/bin:$JAVA_HOME/bin:$PATH"  // Ensure Maven and Java are in the PATH
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

