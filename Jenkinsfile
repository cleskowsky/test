pipeline {

    agent any

    stages {
        stage('Pre build') {
            steps {
                sh 'printenv'
            }
        }

        stage('Source') {
            steps {
                git branch: 'main', url: 'https://github.com/cleskowsky/test2.git'
            }
        }

        // build
        stage('Build') {
            steps {
                echo 'hello, world'
                echo 'hi ma!'
            }
        }

        // test
        // deploy
        stage('Deploy') {
            steps {
                jiraSendDeploymentInfo(
                        environmentId: 'staging',
                        environmentName: 'staging',
                        environmentType: 'staging'
                )
            }
        }
    }
}
