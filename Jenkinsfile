pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        GREETING = 'Hello jenkins'
    }
    options {
        timeout(time: 1, unit: 'SECONDS') 
    }
    // build
    stages {
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
                sh """
                    echo "Here i wrote shell script"
                    echo "$GREETING"
                """
            }
        }
    }
    // Post build means build ipoena tharuwatha em cheyali 
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'This runs when pipeline is failed , used generally to send some alerts !'
        }
        success { 
            echo 'I will say Hello when pipeline is success !'
        }
    }
}