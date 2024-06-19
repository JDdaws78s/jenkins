pipeline {

    agent {
        label 'agent-1'
    }

    options {
        timeout(time: 1 , unit: 'MINUTES')
    }

    environment {
        deploy_to = 'production and'
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('build') {
            steps{
                sh 'echo this is build'
            }
        }
        stage('Test') {
            steps{
                sh 'echo This is test'
            }
        }
        stage('Deploy') {
            steps{
                sh 'echo this is deploy'
            }
        }
        stage('parameters') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"            
            }
        }
    }

    post {
        always {
            echo 'this run always'
        }
        success {
            echo 'this run when success'
        }
        failure {
            echo 'this run when failure'
        }
    }
}