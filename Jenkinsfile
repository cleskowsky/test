pipeline {

    agent any

    stages {
        stage('Source') {
            steps {
                git branch: 'main', url: 'https://github.com/cleskowsky/test2.git'
            }
        }
    }
}
