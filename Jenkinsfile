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
                echo 'in build'
            }
        }

        // test
        // deploy
        stage('Deploy') {
            steps {
                echo 'in deploy'
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
    }
}
