#!/usr/bin/env groovy

pipeline {
    agent any

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

    stages {
        stage('Build') {
            steps {
                script {
                    build(job: "job1",
                        parameters:
                        [string(name: 'Nodes', value: "${params.Nodes}"),
                        string(name: 'Versions', value: "${params.Versions}")
                        ])
                }
            }
        }
        
    }

}
