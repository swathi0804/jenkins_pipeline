pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
                // bat "rmdir  /s /q jenkins_pipeline"
                // bat "git clone https://github.com/swathi0804/jenkins_pipeline.git"
                bat "mvn clean -f jenkins_pipeline"
            }
        }
        stage('install') {
            steps {
                bat "mvn install -f jenkins_pipeline"
            }
        }
        stage('test') {
            steps {
                bat "mvn test -f jenkins_pipeline"
            }
        }
        stage('package') {
            steps {
                bat "mvn package -f jenkins_pipeline"
            }
        }
        stage ('helm build'){
            steps {
                bat "helm install jenkins_pipeline/sample --values values.yaml"
            }
        }
    }
}
