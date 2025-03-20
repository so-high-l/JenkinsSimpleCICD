pipeline {
    
    agent {
        node {
            label 'docker-agent-python'
        }
    }

    triggers {
        pollSCM '* * * * *'
    }

    stages {
        stage ('Build') {
            steps {
                echo "Doing building stuff ..."
                sh 'python --version'
            }
        }

        stage ('Test') {
            steps {
                echo "Doing testing stuff ..."
            }
        }

                stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "Doing delivery stuff ..."
                '''
            }
        }
    }
}