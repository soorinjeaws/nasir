pipeline{
    agent {
        node {
            label  "java-slave"   
            
        }

    }
    stages{
        stage('build') {
            steps{
            echo " ----build-started----- "
            sh 'mvn clean deploy -Dmaven.test.skip=true'
        }
        }
    }


}
