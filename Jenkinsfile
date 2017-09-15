#!/usr/bin/env groovy

pipeline {
    agent any
    
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
                echo "${params.Invoke_Parameters}"
                    if ("${params.Invoke_Parameters}" == "Yes") {
                        currentBuild.result = 'ABORTED'
                        error('DRY RUN COMPLETED. JOB PARAMETERIZED.')
                    }
                }
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
