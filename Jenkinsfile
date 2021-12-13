properties([pipelineTriggers([githubPush()])])
pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'python:3-alpine'
                }
            }
            steps {
                step([$class: 'CordellWalkerRecorder'])
                git branch: 'main', url: 'https://github.com/GalSh5/newtest.git'
                withEnv(["HOME=${env.WORKSPACE}"]) {
                    sh 'pip install --user pytest'
                    sh 'pytest -vv'
                }
            }
        }
    }
}
