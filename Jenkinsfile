pipeline {
    agent none
    stages {
        
        stage('Non-parallel stage') {
            agent {
                label "master"
            }
            steps {
                echo "This stage will be executed first"
            }
        }
        
        stage ("run tests") {
            parallel {
                stage("test on windows") {
                    agent {
                        label "Windows_Node"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                }
                
                stage("Test on Master") {
                    agent {
                        label "master"
                    }
                    steps {
                        echo "Task1 on Master"
                    }
                }
                
            }
        }
    }
}
