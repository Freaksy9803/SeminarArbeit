pipeline {

    agent any
    tools {
        maven 'Maven'
    }
    stages {

        stage('Build') {
            steps {
                bat "mvn clean install"
            }
        }

        stage('Test') {
            when {
                expression {
                    BRANCH_NAME == 'dev'
                }
            }
            steps {
                bat "mvn test"
            }
        }

        stage('Deploy') {
            steps {
                echo 'mvn deploy'
            }
        }
    }
}

