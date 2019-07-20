pipeline {
    agent any
    tools {
        maven 'local_maven'
        jdk 'local_jdk'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${MAVEN_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn clean package sonar:sonar'
            }
            post {
                success {
                    echo "Hello Tests"
                }
            }
        }
    }
}
