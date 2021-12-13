properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/GalSh5/newtest.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
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
