pipilne {
    agent  { label 'kavya'} {
        stages {
            stage ('build') {
                steps {
                    script {
                        sh """
                        echo "Hello, its a build"
                        sh """
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