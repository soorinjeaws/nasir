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
        stage('sonaranalysys') {
            environment {
                scannarHome = tool 'valaxy-sonarscanner'
            }
            steps {
                echo "*********sonar-analysys**********"
                withSonarQubeEnv('valaxy-sonarqube-server') {
                    sh "{$scannarHome}/bin/sonar/sonar-scanner"
                }
                echo "*********sonar-analysys**********"
            }
        }
    }
}

