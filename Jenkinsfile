pipeline {

    agent any
    tools{
        maven 'Maven'
    }
    stages {

        stage('Build') {
            steps {
                sh "mvn clean install"
            }
        }

        stage('Test') {
            when {
                expression {
                    BRANCH_NAME == 'dev'
                }
            }
            steps {
                sh "mvn test"
            }
        }

        stage('Deploy') {
            steps {
                echo 'mvn deploy'
            }
        }
    }
}

