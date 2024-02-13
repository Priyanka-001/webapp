pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn -B -DskipTests clean package'
            }
        }
        
  stage('SonarQube Analysis') {
    steps{
      bat "mvn clean verify sonar:sonar -Dsonar.projectKey=applicationweb -Dsonar.projectName='applicationweb' -Dsonar.host.url=http://localhost:9000 -Dsonar.token=squ_0323a6ce5677e6ab441fc73ce54381a7b1f41037"
    }
  }
}
}
