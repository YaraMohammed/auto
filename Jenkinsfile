#!/usr/bin/env groovy

pipeline {
    agent any

    //this is a work around to skip defining all the parameters in advance for the triggered job
    //at first run set to Invoke_Parameters to Yes this will first dry run, which sets the parameters, 
    //and at the second run, you can run the job as a parameterized job even if you didn't create it as one.
    //at second run set Invoke_Parameters to No
        parameters {
            choice(
                name: 'Nodes',
                choices:"Linux\nMac",
                description: "Choose Node!")
            choice(
                name: 'Versions',
                choices:"1.0\n2.0",
                description: "Build for which version?" )
            choice(
                name: 'Invoke_Parameters', 
                choices:"No\nYes", 
                description: "Do you whish to do a dry run to grab parameters?" 
                )
    }

    //stage to build job1 and pass the parametetrs to it 
    stages {
        stage('Build') {
            steps {
                script {
                    build(job: "job1",
                        parameters:
                        [string(name: 'Nodes', value: "${params.Nodes}"),
                        string(name: 'Versions', value: "${params.Versions}"),
                        string(name: 'Invoke_Parameters', value: "${params.Invoke_Parameters}")
                        ])
                }
            }
        }
        
    }

}
