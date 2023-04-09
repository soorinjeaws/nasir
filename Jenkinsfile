pipeline {
    agent {
        node {
            label "java-slave"
        }
    }
    stages {
        stage('build') {
            steps {
                echo "----build-started----"
                sh '/opt/apache-maven-3.9.1/bin/mvn clean install -Dmaven.test.skip=true'
            }
        }
        stage("Sonar Analysis") {
            environment {
               scannerHome = tool 'valaxy-sonarscanner'
            }
            steps {
                echo '<--------------- Sonar Analysis started  --------------->'
                withSonarQubeEnv('valaxy-sonarqube-server') {    
                    sh "${scannerHome}/bin/sonar-scanner"
                }    
                echo '<--------------- Sonar Analysis stopped  --------------->' 
            }   
        }
    }
}

