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
            mail (to: 'eng.yara4@gmail.com',
                subject: "Jenkins",
                body: "Build is done successfully.");
        }
    }
}
