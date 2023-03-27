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
            sh '/opt/apache-maven-3.9.1/bin/mvn clean install -Dmaven.test.skip=true'
        }
        }
    }


}
