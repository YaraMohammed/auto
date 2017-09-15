pipeline {
    agent any


    stages {
        stage('Build') {
            steps {
            
            //creating jar file with the name as variable
                /*
                sh 'echo $BUILD_NUMBER';
                sh 'javac HelloWorld.java';
                sh 'jar cf HelloWorld_V."$BUILD_NUMBER".jar HelloWorld.class';
                sh 'ls'
                */
                
                
                //'env' in jenkins global variables are accessible as environment variables in shell
                sh """
                echo $BUILD_NUMBER
                echo $BUILD_NUMBER
                env
                """
                
                //trying groovy syntax
                print currentBuild.currentResult
                
                print "We Are Awesome"
            }
        }
        
    }
    post {
        success{
        // 'currentBuild' variables in jenkins global variables are accessible through groovy syntax
        // 
            print "current build in post:    "+currentBuild.number
            print "current build result in post:    "+currentBuild.currentResult
            
        //trying env in groovy
            print "env:     "+env.BUILD_NUMBER
        }
        /*
        success{
            build job: 'test', parameters: [string(name: 'VAR', value: "${BUILD_NUMBER}")]
        }
        */
    }
}
