pipeline {

    agent any

    options {
        buildDiscarder(logRotator(numToKeepStr: '7'))
    }

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
    }
    
    post {
        always {
            jiraSendDeploymentInfo(
                    environmentId: 'nightly',
                    environmentName: 'nightly',
                    environmentType: 'development'
            )
        }
    }
}
