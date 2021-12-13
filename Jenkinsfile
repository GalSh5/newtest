properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any
    stages {
        stage('CheckoutModule1') {
            steps {
                sh 'mkdir -p Module1'
                dir("Module1") {
                    git branch: 'main', url: 'https://github.com/GalSh5/newtest.git'
                }
            }
        }
        stage('CheckoutModule2') {
            steps {
                sh 'mkdir -p Module2'
                dir("Module2") {
                    git branch: 'main', url: 'https://github.com/GalSh5/testrepo.git'
                }
            }
        }
        stage('Test') {
            steps {
                sh 'ls -l Module{1..2}'
            }
        }
    }
}
