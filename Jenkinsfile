#!/usr/bin/env groovy

pipeline {
    agent any
    
    //this is a work around to skip defining all the parameters in advance
    //at first run set to Yes from the triggering job this will first dry run, which sets the parameters, 
    //and at the second run, you can run the job as a parameterized job even if you didn't create it as one.
    //at second run set to No
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

        
        //testing parameters passed correctly
        stage("params")
        {
            steps {
            echo "${params.Nodes}"
            }
        }
}
}
