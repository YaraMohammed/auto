#!/usr/bin/env groovy

pipeline {
    agent any
    
        /*
        parameters {
            choice(
                name: 'Nodes',
                choices:"alphine\nWin",
                description: "Choose Node!")
            choice(
                name: 'Versions',
                choices:"5.0\n6.0",
                description: "Build for which version?" )
        }
    */

            parameters {
                choice(
                name: 'Invoke_Parameters', 
                choices:"No\nYes", 
                description: "Do you whish to do a dry run to grab parameters?" 
                )
            }

    stages {
        stage("parameterizing") {
            steps {
                script {
                    if ("${params.Invoke_Parameters}" == "Yes") {
                        currentBuild.result = 'ABORTED'
                        error('DRY RUN COMPLETED. JOB PARAMETERIZED.')
                    }
                }
            }
        }
        
        stage("echo")
        {
            steps {
            echo hello
            }
        }
        
        stage("params")
        {
            steps {
            echo "${params.Nodes}"
            }
        }
}
}