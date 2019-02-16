pipeline {
    agent any
    stages {
        stage("Compile") {
            steps {
                echo "compile..."
            }
        }
        stage("Unit test") {
            steps {
                echo "unit test..."
            }
        }
       stage("Deployment") {
            steps {
                echo "deployment..."

                dir("deployment") {
                    sh "pwd"

                    ansiColor('xterm') {
                        ansiblePlaybook(credentialsId: 'ansible_private_key', inventory: 'hosts', playbook: 'playbook.yml')
                    }

                }
            }
       }
    }
}
