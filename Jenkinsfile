pipeline {
        agent any
        stages {
               stage('one') {
                steps {
                    echo "hi this is Khavi"
                }
            }
            
            stage('two') {
                steps {
                    input('Do you want to proceed?')
                }
            }

            stage('three') {
                when {  
                    not {
                        branch "master"
                    }
                }
                steps {
                    echo "hello"
                }
            }
            
            stage('four') {
                    parallel {
                        stage('Unit Test') {
                                   steps {
                                    echo "Runnit the unit test ..."
                                    }
                        }
                        stage('Integration test') {
                                   agent {
                                    docker {
                                        reuseNode false
                                        image 'ubuntu'
                                    }
                                    }
                                    steps {
                                     echo "running the integration test"
                                    }
                        }
                    }

}
}
}
