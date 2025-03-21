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
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }

        stage ('Test') {
            steps {
                echo "Doing testing stuff ..."
                sh '''
                cd myapp
                python3 hello.py 
                python3 hello.py --name=Souhail
                '''
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