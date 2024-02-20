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

    stage('Test') {
      post {
        always {
          junit 'target/surefire-reports/*.xml'
        }

      }
      steps {
        bat 'mvn test'
      }
    }

    stage('Sonar-Report') {
      steps {
        bat 'mvn clean verify sonar:sonar -Dsonar.projectKey=project-test -Dsonar.projectName=\'project-test\' -Dsonar.host.url=http://localhost:9000 -Dsonar.token=squ_3bf61d206e6a865ed854de1eeaaee711fd604775'
      }
    }

    // stage('Deploy') {
    //   steps {
    //     bat 'java -jar C:\\Users\\priya\\Jenkins_\\workspace\\Webapp\\target\\java-webapp-1.0.jar'
    //   }
    // }

  }
}
