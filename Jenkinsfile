pipeline {
    agent { label 'kavya' }

    environment {
        PROJECT   = 'expense'
        COMPONENT = 'backend'
        DEPLOY    = 'qa'
    }

    options {
        disableConcurrentBuilds()
        timeout(time: 10, unit: 'MINUTES')
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {

        stage('Build') {
            steps {
                sh '''
                    echo "Hello, this is build"
                    echo "Project: $PROJECT"
                    echo "Hello ${PERSON}"
                    echo "Biography: ${BIOGRAPHY}"
                    echo "Toggle: ${TOGGLE}"
                    echo "Choice: ${CHOICE}"
                '''
                sleep 5
            }
        }

        stage('Test') {
            when {
                environment name: 'DEPLOY', value: 'qa'
            }
            steps {
                sh '''
                    echo "Hello, this is test"
                '''
            }
        }

        stage('Deploy') {
            input {
                message "Should we continue?"
                ok "Yes we should"
            }
            steps {
                sh '''
                    echo "Hello, this is deploy"
                '''
            }
        }
    }
 stage('Parallel Stages') {
            parallel {
                stage('STAGE-1') {
                    
                    steps {
                        script{
                            sh """
                                echo "Hello, this is STAGE-1"
                                sleep 15
                            """
                        }
                    }
                }
                stage('STAGE-2') {
                    
                    steps {
                        script{
                            sh """
                                echo "Hello, this is STAGE-2"
                                sleep 15
                            """
                        }
                    }
                }
            }
        }
    }

    post {
        always {
            echo "I will say hello again"
        }
        failure {
            echo "I will run when pipeline fails"
        }
        success {
            echo "I will run when pipeline succeeds"
        }
    }
}
