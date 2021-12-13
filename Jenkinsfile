properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any
    // comment
    stages
        stage ('Checkout'){
            git branch: 'main', url: 'https://github.com/GalSh5/newtest.git'
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
    }
}
