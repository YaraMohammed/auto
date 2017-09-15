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
                //'env' in jenkins global variables are accessible as environment variables in shell
                sh 'echo $BUILD_NUMBER'
            }
        }
        
    }
    post {
        success{
        // 'currentBuild' variables in jenkins global variables are accessible through groovy syntax
        // 
            print currentBuild.result
            print env.BUILD_NUMBER
        }
        /*
        success{
            build job: 'test', parameters: [string(name: 'VAR', value: "${BUILD_NUMBER}")]
        }
        */
    }
}
