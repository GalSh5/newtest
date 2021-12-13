properties([pipelineTriggers([githubPush()])])

pipeline {
    agent 
    stages {
        stage('Checkout') {
            steps {
                step([$class: 'CordellWalkerRecorder'])
                git branch: 'main', url: 'https://github.com/GalSh5/newtest.git'
            }
        }
        stage('Build') {
            steps {
                sh 'pip install pytest'
            }
        }
        stage('Test') {
            steps {
                sh 'pytest'
            }
        }i
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
