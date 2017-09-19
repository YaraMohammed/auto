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
        stage("input"){
            steps {
            echo "running"
            def branchInput = input message: 'Please input branch to test against', parameters: [[$class: 'StringParameterDefinition', defaultValue: 'master', description: '', name: 'branch']]
            echo "BRANCH NAME: ${branchInput}"
        }
        
    }
    }
        /*
    post {
        success{
     build job: 'test', parameters: [string(name: 'VAR', value: sh 'echo $BUILD_NUMBER')]
        }
    }
    */
}
