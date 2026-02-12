pipeline {
    agent  { label 'kavya'}
    environment {
        project = 'expense'
        
        component = 'backend'
deploy = "qa"

    } 

    options {
        disableConcurrentBuilds()
        timeout (time: 344443385, unit: 'SECONDS')
    }
     parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
        stages {
            stage ('build') {
                steps {
                    script {
                        sh """
                       echo "Hello, this is build"
                    echo "Project: $PROJECT"
                    echo "Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password: ${params.PASSWORD}"

                        sh """
                        sleep 15
                    }
                }
            }

            when {
                environment name: 'deploy'  value:'prod'
            }

            stage ('test') {
                steps {
                    script {
                        sh """
                        echo "hello its a test"
                        sh """
                    }
                }
            }

            stage ('Deploy') {
                input {
                    message "shouls we contine"
                    ok "yes we should"
                }
                steps {
                    script {
                        sh """
                        echo "hello its deploy"
                        sh """
                    }
                }
            }
        }
    


post {
    always {
        echo " i will say hellow again"
    }

    failure {
        echo "i wikk run when pipeline is failed"
    }

    success{
        echo "i will run when pipleine is sucess"
    }
}
}