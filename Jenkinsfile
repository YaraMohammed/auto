pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                input 'You are awesome, Do you agree?';
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
