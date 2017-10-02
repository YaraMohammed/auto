pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh'cd ayhaga'
            }
        }
    }
    post {
        success{
            echo 'success'
        }
        failure{
            echo 'fail'
        }
    }
}
