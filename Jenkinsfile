pipeline {
    agent { 
        node {
            label 'agent-python'
            }
      }
    triggers {
	pollSCM '* * * * *'
      }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd my_app
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd my_app
                python3 hello.py
                python3 hello.py --name=Salazar
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
