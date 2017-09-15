#!/usr/bin/env groovy

pipeline {
    agent any
    
        agent any
        parameters {
            choice(
                name: 'Nodes',
                choices:"Linux\nMac",
                description: "Choose Node!")
            choice(
                name: 'Versions',
                choices:"1.0\n2.9",
                description: "Build for which version?" )
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
