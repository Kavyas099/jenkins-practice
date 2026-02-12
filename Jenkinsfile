pipeline {
    agent  { label 'kavya'}
    environment {
        project = 'expense'
        
        component = 'backend'


    } 

    options {
        disableConcurrentBuilds()
        timeout (time: 5, unit: 'seconds')
    }
        stages {
            stage ('build') {
                steps {
                    script {
                        sh """
                        echo "Hello, its a build"
                        echo : "project : $project"
                        sh """
                        sleep 15
                    }
                }
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