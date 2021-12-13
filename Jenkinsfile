pipeline {
    agent none
    stages {
        stage('Checkout') {
            steps {
                step([$class: 'CordellWalkerRecorder'])
                git branch: 'main', url: 'https://github.com/GalSh5/newtest.git'
            }
        }
        stage('Build') {
            agent {
                docker {
                    image 'python:3-alpine'
                }
            }
            steps {
                withEnv(["HOME=${env.WORKSPACE}"]) {
                    sh 'pip install --user pytest'
                    sh 'pytest -vv'
                }
            }
        }
    }
}
