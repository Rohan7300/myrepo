pipeline{
    agent any

     tools {
        maven 'Maven1' 
    }
    stages{
        stage("Test"){
            steps{
                //mvn
                sh "mvn --version"
                sh "mvn test"
                echo "========executing A========"
            }
        }

          stage("Build"){
            // mvn package
            steps{
                sh "mvn package"
                echo "========executing A========"
            }
        }

          stage("Deploy"){
            steps{

                deploy adapters: [tomcat9(credentialsId: '4172c0f2-c23e-4068-aaf0-792c4eb50cdd', path: '', url: 'http://192.168.0.108:5500')], contextPath: '/user', war: '**/*.war'
                //deploy container
                echo "========executing A========"
            }
        }

          stage("Production"){
            steps{

                //same container
                echo "========executing A========"
            }
        }
        
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
