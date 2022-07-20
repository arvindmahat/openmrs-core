pipeline {
    agent { label 'build_java_11' }
    stages {
        stage('SourceCode') {
            steps {
                git branch: 'master', url: 'https://github.com/arvindmahat/openmrs-core.git'
            }
        }
        stage('Build the code') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Build the image') {
            steps {
                sh 'cd openmrs-core'
                sh 'docker build -t myopenmrs:1.0 .'
            }
        }
    }
}
