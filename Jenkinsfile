pipeline {
    agent any


    stages {
        stage('Build') {
            steps {
                /*
                sh 'echo $BUILD_NUMBER';
                sh 'javac HelloWorld.java';
                sh 'jar cf HelloWorld_V."$BUILD_NUMBER".jar HelloWorld.class';
                sh 'ls'
                */
                sh 'echo $BUILD_NUMBER'
            }
        }
        
    }
    post {
        success{
            script{
                echo currentBuild.number
            }
        }
        /*
        success{
            build job: 'test', parameters: [string(name: 'VAR', value: "${BUILD_NUMBER}")]
        }
        */
    }
}
