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
                  python3 -m venv .venv           # Create a virtual environment
                  . .venv/bin/activate            # Activate it
                  pip install --upgrade pip       # Upgrade pip inside the venv
                  pip install -r requirements.txt # Install dependencies
                '''
            }
        }

        stage ('Test') {
            steps {
                echo "Doing testing stuff ..."
                sh '''
                  cd myapp
                  . .venv/bin/activate
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
