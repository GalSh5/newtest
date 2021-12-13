properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                step([$class: 'CordellWalkerRecorder'])
                git branch: 'main', url: 'https://github.com/GalSh5/newtest.git'
            }
        }
        stage('Build') {
            steps {
                sh 'virtualenv venv && . venv/bin/activate && pip install -r pytest'
            }
        }
        stage('Test') {
            steps {
                sh 'pytest'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Testing Parallel') {
            parallel {
                stage("number 1") {
                    steps {
                        echo "blabla"
                    }
                }
                stage("number 2") {
                    steps {
                        echo "pokpok"
                    }
                }
            }
        }
    }
}
