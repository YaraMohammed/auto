pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                input 'hello dear lets test?';
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
