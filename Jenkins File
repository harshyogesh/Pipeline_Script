pipeline {
    agent none
    stages{
        stage ('non parallel stage'){
            agent {
                label "master"
            }
            steps{
                echo "this is the fist step which is non-parallel"
            }
        }
        stage ('unit-tests'){
            parallel{
                stage ('winodows-test'){
                    agent{
                        label "Slave_one"
                    }
                        steps{
                            echo "this is job 1 which is executing on a slave in parallel to a job on master"
                        }
                    }
                
                stage('linux-test'){
                    agent{
                        label "master"
                    }
                    steps{
                        echo "this is job2 executng on master in parallel to a job executing on slave"
                    }
                }
            
            }        
        }
    }
        
}
