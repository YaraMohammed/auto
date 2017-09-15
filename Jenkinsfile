pipeline {
    agent any
    /*
    environment {
        x = ${BUILD_NUMBER}
    }
    */

    stages {
        stage('Build') {
            steps {
                /*
                sh 'echo $BUILD_NUMBER';
                sh 'javac HelloWorld.java';
                sh 'jar cf HelloWorld_V."$BUILD_NUMBER".jar HelloWorld.class';
                sh 'ls'
                ${BUILD_NUMBER}
                */
                sh 'echo $BUILD_NUMBER'
            }
        }
        
    }
    post {
        success{
             build job: 'test', parameters: [string(name: 'VAR', value: "${BUILD_NUMBER}")]
        }
    }
}
